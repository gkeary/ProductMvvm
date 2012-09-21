2 files for VT configuration now under bersion control
======================================
c:\t1\VT2.Dispatch2.exe.comfig
c:\t1\VT3.Dispatch2.exe.comfig


git tag V2.62
===============
fixed bug in frmInput CustomerID_keydown
   now seeks to partial match
   should also finish out population of CustomerID...
   changed order of steps after if count = 1 and this fixed it.


git tag V2.61
===============
has partial matches
pushed to VT2


Without listboxPreview
========================
=======
Put out to D26a
================



Partial match
=================
Customer maintenance error message needs a cancel button --DONE

c should partial match --DONE
con should partial match --DONE


Pre-release Testing
====================

InputForm_Load was throwing (array out of bounds)  --DONE
Close Routes Throws -- Disabled CloseRoutes menu Item...
  now you can Set-Routes-For-Today, Start-of-Day, End-of-Day, close it.

Disable mainform  X out if After End-of-Day
Put message into menu Exit 


Examining OnetimePickupScreen
==============
Customer City shows '51' or '50'  vice  Williston etc...
Save and Close THROWS...  added Assertions,  added messageboxes

Doubleclick listbox does nothing.  It should populate fields  --DONE
SelectedIndexChanged does not populate the fields --DONE
Improve Recurring Pickup Menu Structure
Click custID popultes fields from <selected> --DONE
Check Save for lies.
check save and close for lies.
Look for Tim's problem...
refine the helpful text in the white box.

now it says:
"Enter CustID  and <CR> for quick data entry"
 "Use <tab key> to cycle from CustID to Listbox to NewPickupText"
 "With focus in ListBox, alphabetic keys move to <first entry>  e.g. 'K' moves to th" & _
     "e K's", """DP"" in NEW Pickup Text sets a Daily Pickup e.g.  Pickup EVERY day.", """DP""  with Tuesday  sets a Pickup EVERY Tuesday."})
  

Source Code Delivery
=================
put a copy on NHDISPATCH2003  && VT1 && VT2
push to Githup
Give Calvin a github login
put on a memstick
burn a CD   (V2.6 dtd 05/05/2012)


Merge DeleteCustBug to master
================

Add a confirm button before delete occurs...  DONE



Silicone Oil
===============
from Ivana Kim:   (4/30/2012) 
  conditions exist:  Silicone oil, abnormal blood vessels on Iris, scar tissue on intraocular lens
  procedure(s) proposed for evaluating and treating my condition(s) are
          removal of silicone oil
	  removal of scar tissue on lens,
     	  possible injection of Avastin,
	  possible injection of gas bubble,
	  removal of lens if necessary   (left eye)


Decisions based on the notes below
================

Clear out CustID.text and StringSoFar upon mouse entry (in the input window...)
Input window was duplicated  now it does not refresh... DONE  (now has Refresh Customer List button)

you cannot add a customer.  keydown routine is malfunctioning....  DONE (now checks for "not FormMode = 'ADD')



test and refine moving lstboxCustomer.selected via text input in CustID DONE
put a menu on frmCustomer DONE
validate each field when stepping out DONE
move buttons to the top DONE
dedicate one button to Edit/New another to Delete DONE
Have ValidateCustomer build and return an error string DONE
Have ValidateCustomer change background color for bad fields. DONE
Have ClearForm (or a new routine?) reset the background color DONE

Use paper and pencil for testing.
Test Add Edit Delete  w/  1,2,3... invalid errors w/o invalid errors
  6 cases

Listboxes were not sorted the same.  This was cased by me.listboxCustomer.sorted = true   in frmInput.Designer.vb !!! DONE

Branch: DeleteCustBug
=======
4/28/2012  the cabin...

*  early notes (mostly superceded)
  ChangeMode() should only handle buttons
  Each button push must depend on radiobutton selection
  DeleteCustomerAndPickup doesn't show message
     if notHelper.HasCDP("AAAAA")  cust.delete

Throws @ Helpe.GetROUTE2DefaultDriverID
   so have helper methods test and return a value
    have customer save validate DefaultDriverID
** bugs found in the customer screen...

Delete does not refresh mCustomerCollection (this symptom still there)
Save New Customer gives zero feedback
Closing Customer Maintenance does not refresh InputForm.lstboxCustomer
InputForm isusing itsOWN mCustomerCollection
Save Customer allows Duplicat CustomerID's




Vermont visit bugs
=======
4/24/2012

a. Modify VT1 && VT2 for 2 station posting vice 3  DONE
b. Recurring Pickup Bug
c. Delete Customer Bug
d. Better Size For Edit Routes Form
e. Validate Pickup On Edit
f. Validate Pickup On Creation
g. Customer Screen Startup Is Slow
h. Make Customer Delete Button Disappear on Selected Index change

edit-cust-posting-bug
=======
4/19/2012

edit a customre (e.g. change contact to Laura R)
then post a new pickup with that customer.
see that it does not post and/or receive the post???

also:  fixed the mainform location and size upon application exit.
also:  fixed the validation of DriverID in frmDefaultRoute.vb...


Memory leak tests in VS2010
=======
4/6/2012


Testing of CREATE POSTING ROUTINES.
=======
3/31/2012

Manual tests.  SEE ROSS NOTEBOOK FOR RESULTS MATRIX

For 1 station to 3 stations.
 if 2 or three stations
    for Station1
    for Station2
     for Station3
a  for CDP 
  a1   add
  a2   change
   a3   drag-drop
  for CDR changes
    b1  Driver Text change
   for Customer
    c1   edit a customer
     c2  add a customer

previous Master version had onetimepickup->addpickup customerID disabled
=======
2/7/2011
worked on Tim's problem:  i.e.  too many Route2's
backed up D2_VT..




tag VT2.02 is the asbuilt for WRJ visit on 4/21/11


Steps to run from elwood to jake:
a:  install sqlexpress v10 on Jake
b.  connect to sqlexpress on jake   i.e.  jake\abby
c.  enable tcp on jake\abby
d.  connect w/ ssms from elwood to jake\abby
e.  point app.config at jake\abby  d2_vt and run from VS2008
f.  edit \c\trunk\dispatch2\bin\debug\Dispatch2.exe.config  so connection string is correct

UREEKA!!!



this repository is for Ross Dispatch 2011


helpful articles about connection strings...

1. All SQL Server SqlConnection Propeties:

http://www.connectionstrings.com/Articles/Show/all-sql-server-connection-string-keywords

2. What is a connection string?
http://www.connectionstrings.com/Articles/Show/what-is-a-connection-string

3. Rules for connection strings:

http://www.connectionstrings.com/Articles/Show/important-rules-for-connection-strings

4.SQL Server Data Types Reference:

http://www.connectionstrings.com/Articles/Show/sql-server-data-type-reference


