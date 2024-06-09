# studimport java.util.Scanner;

public class StudentManagementSystem {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Get student details from user input
        System.out.print("Enter student ID: ");
        int studentId = scanner.nextInt();
        scanner.nextLine(); // Consume the newline character
        System.out.print("Enter student name: ");
        String name = scanner.nextLine();
        System.out.print("Enter student age: ");
        int age = scanner.nextInt();

        // Get course details from user input
        System.out.print("Enter course ID: ");
        int courseId = scanner.nextInt();
        scanner.nextLine(); // Consume the newline character
        System.out.print("Enter course name: ");
        String courseName = scanner.nextLine();

        // Get grade from user input
        System.out.print("Enter grade: ");
        double grade = scanner.nextDouble();

        // Create student, course, and grade objects
        Student student1 = new Student(studentId, name, age);
        Course course1 = new Course(courseId, courseName);
        Grade grade1 = new Grade(student1, course1, grade);

        // Display student information, course information, and grade
        System.out.println("\nStudent Information:");
        System.out.println("ID: " + student1.getStudentId());
        System.out.println("Name: " + student1.getName());
        System.out.println("Age: " + student1.getAge());

        System.out.println("\nCourse Information:");
        System.out.println("ID: " + course1.getCourseId());
        System.out.println("Name: " + course1.getCourseName());

        System.out.println("\nGrade: " + grade1.getGrade());

        scanner.close();
    }
}

class Student {
    private int studentId;
    private String name;
    private int age;

    public Student(int studentId, String name, int age) {
        this.studentId = studentId;
        this.name = name;
        this.age = age;
    }

    public int getStudentId() {
        return studentId;
    }

    public String getName() {
        return name;
    }

    public int getAge() {
        return age;
    }
}

class Course {
    private int courseId;
    private String courseName;

    public Course(int courseId, String courseName) {
        this.courseId = courseId;
        this.courseName = courseName;
    }

    public int getCourseId() {
        return courseId;
    }

    public String getCourseName() {
        return courseName;
    }
}

class Grade {
    private Student student;
    private Course course;
    private double grade;

    public Grade(Student student, Course course, double grade) {
        this.student = student;
        this.course = course;
        this.grade = grade;
    }

    public double getGrade() {
        return grade;
    }
}
