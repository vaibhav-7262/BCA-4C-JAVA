# BCA-4C-JAVA
Dear Students, Java first assignment need to complete on time

Encapsulation in Java is the process by which data (variables) and the code that acts upon them (methods) are integrated as a single unit. By encapsulating a class's variables, other classes cannot access them, and only the methods of the class can access them. 
Create a class EMPLOYEE having data members as NameOfEmp, Emp-Id, BasicSalary and GrossSalary. NameOfEmp, Emp-Id, BasicSalary should be entered as user input. Calculate HRA (HRA is 25% of BasicSalary).Also, calculate DA (DA is 40% of BasicSalary). Then, calculate GrossSalary (GrossSalary=BasicSalary+HRA+DA). 
Implement the following queries: 
a) Display the NameOfEmp and GrossSalary of employees whose name starts With a consonent.
b) Display the Emp-Id and GrossSalary of Employees whose Emp-Id is between 101 and 150.
c) Count the total number of Employees whose GrossSalary is less than 35000/-


package java_lab;
import java.util.*;

class Employees{
	private String name;
	private double basicSalary;
	private int id;
	
	void getData() {
		Scanner scan = new Scanner(System.in);
		this.id = scan.nextInt();
		this.name = scan.next();
		this.basicSalary = scan.nextDouble();
	}
	
	String returnName() {
		return this.name;
	}
	
	double getHRA() {
		return this.basicSalary*(25/100);
	}
	double getDA() {
		return this.basicSalary*(40/100);
	}
	double returnGrossSalary() {
		return this.basicSalary+getHRA()+getDA();
	}
	
	int getId() {
		return this.id;
	}
}
public class assignment {
	public static void main(String args[]) {
		int num;
		Scanner scan = new Scanner(System.in);
		System.out.print("Enter num of employees: ");
		num = scan.nextInt();
		Employees[] emp = new Employees[num];
		
		
		for(int i = 0; i < num; i++) {
			emp[i] = new Employees();
			System.out.printf("Enter student %d id, name and salary:\n" , (i+1));
			emp[i].getData();
		}
		
		int count =0;
		for(int i = 0; i < num; i++) {
			String name = emp[i].returnName();
			double grossSalary = emp[i].returnGrossSalary();
			int id = emp[i].getId();
			
			if(!name.startsWith("a") && !name.startsWith("e") && !name.startsWith("i") && !name.startsWith("o") && !name.startsWith("u")) {
				System.out.printf("\nname=%s,gross salary=%.2f\n", name, grossSalary);
			}
			
			
		}
		
		for(int i = 0; i < num; i++) {
			double grossSalary = emp[i].returnGrossSalary();
			int id = emp[i].getId();
			if(id > 101 && id < 150) {
				System.out.printf("\nid=%d,gross salary=%s\n", id, grossSalary);
			}
			if(grossSalary < 35000) {
				count++;
		}
	}
		System.out.println("\nperson with less than 35000 salary: ");
		System.out.print(count);
		
	}
}
