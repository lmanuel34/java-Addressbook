# java-Addressbook
A program that stores contact information

Create an AddressBook class in Java for general use with the following behaviors:

1.	Constructor: public AddressBook
Construct a new address book object.
	A contact has four fields: first name, last name, email and phone.  (There could be more information for a real contact.  But these are sufficient for the assignment.)
	The constructor reads from the disk to retrieve previously entered contacts.  If previous contacts exist, the address book will be populated with those contacts retrieved from the disk.  Otherwise, the address book will be empty.
	The constructor should notify the user if any disk I/O error occurs (IOException).
Note: Since the AddressBook class should not include the user interface, the way in which the user is notified should be a correspondingly thrown exception object.  A System.out.println() is NOT appropriate for this method.

2.	Method: public void addContact(Contact newContact)
Add a new contact into the address book:
	Neither the first name nor the last name in newContact can be null or empty (NullPointerException and EmptyNameException, respectively).
	The method should notify the user if a contact with the same first name and last name is already in the address book (DuplicateContactException).   Therefore, newContact will not be inserted.
	When a new contact is added into the address book, the content of the address book should be saved to the disk.  The method should notify the user if any disk I/O error occurs (IOException).  If a disk error does occur, the addition of the new contact should be cancelled, that is, even if the new contact was added into the address book, it should be removed from the address book upon an I/O error so that consistency is maintained between the contacts in memory and those on the disk.

3.	Method: public void deleteContact(String firstName, String lastName)
Delete from the address book a contact whose first name and last name are the same as the input parameters.
	The user needs to provide both the first name and the last name of the contact to be deleted.
	Neither the first name nor the last name can be null or empty (NullPointerException and EmptyNameException, respectively).
	The method should notify the user if a contact with the same first name and last name cannot be found in the address book (ContactNotFoundException).  Thus, deletion does not happen. 
	When a contact is deleted from the address book, the content of the address book should be saved to the disk.  The method should notify the user if any disk I/O error occurs (IOException).  If a disk error does occur, the deletion of the contact should be cancelled, that is, even if the contact was deleted from the address book, it should be recovered in the address book upon an I/O error so that consistency is maintained between the contacts in memory and those on the disk.

4.	Method: public Contact[] searchByLastName(String lastName)
Search all contacts by the last name and return matching contacts as an array of contacts.
	There might be zero or more than one contact returned
	The last name provided cannot be null or empty (NullPointerException and EmptyNameException, respectively).  The user should be notified if the lastName argument is null or empty. 

5.	Method: public Contact[] list()
Return all the contacts in the address book as an array of contacts.

In your implementation, the contacts in the address book should be read from and written into a file named “contacts.dat”.   When the address book is opened again, the contacts previously added should be loaded into the address book from the file.

Your code should provide specifications for all classes, constructors and methods based on the templates given in the lecture notes and the textbook (OVERVIEW, REQUIRES, MODIFIES, EFFECTS, etc.).  

Note that the method headers provided above do not include any throws clause.  If you decide a certain exception object may be thrown from the method, the header should be modified accordingly.  Whenever an exception is needed, if there is no applicable built-in Java API exception, you need to define your own exception and decide whether the exception should be checked or unchecked.


