import java.util.Scanner;

public class RunEmployee {

 public static void main(String[] args) {

 Scanner in = new Scanner(System.in);

 

 System.out.print("Enter Employee Name: ");

 String name = in.nextLine();

 

 System.out.println("\nEmployee Types:\n F - Full Time\n P - Part Time");

 System.out.print("Enter Employee Type:");

 String type = in.nextLine();

 if (type.compareToIgnoreCase("F") == 0) {

 FullTimeEmployee employee = new FullTimeEmployee(name);

 

 System.out.print("\nEnter Monthly Salary: ");

 employee.setMonthlySalary(in.nextDouble());

 

 System.out.println(employee);

 } else if(type.compareToIgnoreCase("P") == 0) {

 PartTimeEmployee employee = new PartTimeEmployee(name);

 

 System.out.print("\nEnter Rate Per Hour: ");

 double rate = in.nextDouble();

 

 System.out.print("\nEnter Number of Hours Worked: ");

 employee.setWage(rate, in.nextInt());

 

 System.out.println(employee);

 } else {

 System.out.println("Error: Ivalid Employee Type!");

 }

 }

}

abstract class Employee {

 private String name;

 public Employee(String name) {

 setName(name);

 }

 

 public void setName(String name) {

 this.name = name;

 }

 

 public String getName() {

 return name;

 }

}

final class FullTimeEmployee extends Employee {

 private double monthlySalary;

 

 public FullTimeEmployee(String name) {

 super(name);

 }

 

 public void setMonthlySalary(double salary) {

 monthlySalary = salary;

 }

 

 public double getMonthlySalary() {

 return monthlySalary;

 }

 

 public String toString() {

 return "\nEmployee Name: " + getName() + "\nMonthly Salary: " + monthlySalary;

 }

}

final class PartTimeEmployee extends Employee {

 private double ratePerHour;

 private int hoursWorked;

 private double wage;

 

 public PartTimeEmployee(String name) {

 super(name);

 }

 

 public void setWage(double rate, int hours) {

 ratePerHour = rate;

 hoursWorked = hours;

 wage = ratePerHour * hoursWorked;

 }

 

 public double getWage() {

 return wage;

 }

 

 public String toString() {

 return "\nEmployee Name: " + getName() + "\nWage: " + wage;

 }

}

package payrollSystem;

public class Employee {

 private String firstName;

 private String lastName;

 private int ID;

 private double hourlyWage;

 private double hoursWorked;

 public Employee(String first, String last, int id, double wage, double hours) {

 firstName = first;

 lastName = last;

 ID = id;

 hourlyWage = wage;

 hoursWorked = hours;

 }
public void setFirstName(String first) {

 this.firstName = first;

 }

 public String getFirstName() {

 return firstName;

 }

 public void setLastName(String last) {

 this.lastName = last;

 }

 public String getLastName() {

 return lastName;

 }

 public void setID(int ID) {

 this.ID = ID;

 }

 public int getID() {

 return ID;

 }

 public void setHourlyWage(double hourlyWage) {

 this.hourlyWage = hourlyWage;

 }

 public double getHourlyWage() {

 return hourlyWage;

 }

 public void setHoursWorked(double hoursWorked) {

 this.hoursWorked = hoursWorked;

 }

 public double getHoursWorked() {

 return hoursWorked;

 }

 public double calcPay(double wage, double hours) {

 wage = getHourlyWage();

 hours = getHoursWorked();

 return wage * hours;

 }

}

PayCheck:

package payrollSystem;

public class PayCheck {

 private String firstName;

 private String lastName;

 private int ID;

 private double netAmount;

 public PayCheck(String first, String last, int id, double wage, double hours) {

 firstName = first;

 lastName = last;

 ID = id;

 netAmount = wage * hours;

 }

 public String toString() {

 return "Paycheck issued for " + netAmount + "to " + firstName + ", "+ lastName + ", 

employee ID " + ID;

 }

}

PayrollSystem:

package payrollSystem;

import java.util.List;

import java.util.ArrayList;

public class PayrollSystem {

 public List<Employee> employees = new ArrayList<Employee>();

 public String companyName;

 PayrollSystem(String company) {

 companyName = company;

 }

 void addEmployee(Employee a) {

 employees.add(a);

 }

 void getHoursWorked(double hrs) {

 this.a.getHoursWorked();

 }

 void issueCheck() {

 double checkAmount = this.a.calcPay(a.getHoursWorked(), a.getHourlyWage());

 PayCheck check = new PayCheck(a.getFirstName(), a.getLastName(), a.getID(), 

a.getHoursWorked(), a.getHourlyWage());

 check.toString();

 }
}
