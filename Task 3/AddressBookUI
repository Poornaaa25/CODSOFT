import java.util.Scanner;

public class AddressBookUI {
    private static AddressBook addressBook = new AddressBook();
    private static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        while (true) {
            showMenu();
            int choice = Integer.parseInt(scanner.nextLine());
            switch (choice) {
                case 1:
                    addNewContact();
                    break;
                case 2:
                    editContact();
                    break;
                case 3:
                    searchContact();
                    break;
                case 4:
                    displayAllContacts();
                    break;
                case 5:
                    System.out.println("Exiting...");
                    return;
                default:
                    System.out.println("Invalid choice. Try again.");
            }
        }
    }

    private static void showMenu() {
        System.out.println("Address Book Menu:");
        System.out.println("1. Add New Contact");
        System.out.println("2. Edit Contact");
        System.out.println("3. Search Contact");
        System.out.println("4. Display All Contacts");
        System.out.println("5. Exit");
        System.out.print("Choose an option: ");
    }

    private static void addNewContact() {
        System.out.print("Enter Name: ");
        String name = scanner.nextLine();
        System.out.print("Enter Phone Number: ");
        String phone = scanner.nextLine();
        System.out.print("Enter Email: ");
        String email = scanner.nextLine();
        System.out.print("Enter Address: ");
        String address = scanner.nextLine();

        if (name.isEmpty() || phone.isEmpty() || email.isEmpty() || address.isEmpty()) {
            System.out.println("All fields are required.");
            return;
        }

        Contact contact = new Contact(name, phone, email, address);
        addressBook.addContact(contact);
        System.out.println("Contact added successfully.");
    }

    private static void editContact() {
        System.out.print("Enter the name of the contact to edit: ");
        String name = scanner.nextLine();
        Contact contact = addressBook.searchContact(name);
        if (contact == null) {
            System.out.println("Contact not found.");
            return;
        }
        System.out.println("Editing contact: " + contact);

        System.out.print("Enter new Phone Number (or press enter to skip): ");
        String phone = scanner.nextLine();
        if (!phone.isEmpty()) {
            contact.setPhoneNumber(phone);
        }

        System.out.print("Enter new Email (or press enter to skip): ");
        String email = scanner.nextLine();
        if (!email.isEmpty()) {
            contact.setEmail(email);
        }

        System.out.print("Enter new Address (or press enter to skip): ");
        String address = scanner.nextLine();
        if (!address.isEmpty()) {
            contact.setAddress(address);
        }

        System.out.println("Contact updated successfully.");
    }

    private static void searchContact() {
        System.out.print("Enter the name of the contact to search: ");
        String name = scanner.nextLine();
        Contact contact = addressBook.searchContact(name);
        if (contact == null) {
            System.out.println("Contact not found.");
        } else {
            System.out.println(contact);
        }
    }

    private static void displayAllContacts() {
        addressBook.displayContacts();
    }
}
