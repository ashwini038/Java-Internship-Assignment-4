//SOLID principles practice
//Refactor the following code following SOLID principle
import java.util.*;
class Employee {
    private String name;
    private double salary;

    public Employee(String name, double salary) {
        this.name = name;
        this.salary = salary;
    }

    public String getName() {
        return name;
    }

    public double getSalary() {
        return salary;
    }
}
class EmployeeDatabase {

    public void saveToDatabase(Employee employee) {
        System.out.println("Employee saved to database: "
                + employee.getName());
    }
}
interface Discount {
    double calculateDiscount(double amount);
}
class RegularCustomerDiscount implements Discount {

    @Override
    public double calculateDiscount(double amount) {
        return amount * 0.10;
    }
}
class PremiumCustomerDiscount implements Discount {

    @Override
    public double calculateDiscount(double amount) {
        return amount * 0.20;
    }
}
class VIPCustomerDiscount implements Discount {

    @Override
    public double calculateDiscount(double amount) {
        return amount * 0.30;
    }
}
interface Workable {
    void work();
}

interface Eatable {
    void eat();
}

interface Sleepable {
    void sleep();
}
class HumanWorker implements Workable, Eatable, Sleepable {

    @Override
    public void work() {
        System.out.println("Human is working");
    }

    @Override
    public void eat() {
        System.out.println("Human is eating");
    }

    @Override
    public void sleep() {
        System.out.println("Human is sleeping");
    }
}
class RobotWorker implements Workable {

    @Override
    public void work() {
        System.out.println("Robot is working");
    }
}
public class Main {

    public static void main(String[] args) {

        System.out.println("Testing SOLID principles...");
        Employee employee = new Employee("Ashiwini", 50000);

        EmployeeDatabase database = new EmployeeDatabase();
        database.saveToDatabase(employee);
        Discount regular = new RegularCustomerDiscount();
        Discount premium = new PremiumCustomerDiscount();
        Discount vip = new VIPCustomerDiscount();

        System.out.println("Regular Discount: "
                + regular.calculateDiscount(1000));

        System.out.println("Premium Discount: "
                + premium.calculateDiscount(1000));

        System.out.println("VIP Discount: "
                + vip.calculateDiscount(1000));
        HumanWorker human = new HumanWorker();
        human.work();
        human.eat();
        human.sleep();

        RobotWorker robot = new RobotWorker();
        robot.work();
    }
}


output:
Testing SOLID principles...
Employee saved to database: Ashiwini
Regular Discount: 100.0
Premium Discount: 200.0
VIP Discount: 300.0
Human is working
Human is eating
Human is sleeping
Robot is working
