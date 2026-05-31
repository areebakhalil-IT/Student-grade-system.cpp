#include <iostream>
#include <fstream>
#include <string>
using namespace std;

int main() {
    string names[5];
    int rollNo[5];
    float marks[5][3]; // 5 students, 3 subjects each
    float total[5];
    float average[5];
    char grade[5];

    int n = 1; 

    cout << "=== Student Grade System with Array ===" << endl;
    for(int i = 0; i < n; i++) {
        cout << "\nEnter details for Student " << i+1 << ":" << endl;
        cout << "Name: ";
        cin >> names[i];
        cout << "Roll No: ";
        cin >> rollNo[i];
        cout << "Enter 3 subject marks: ";
        cin >> marks[i][0] >> marks[i][1] >> marks[i][2];

        // Calculate Total + Average
        total[i] = marks[i][0] + marks[i][1] + marks[i][2];
        average[i] = total[i] / 3.0;

      
        if(average[i] >= 80) grade[i] = 'A';
        else if(average[i] >= 60) grade[i] = 'B';
        else if(average[i] >= 40) grade[i] = 'C';
        else grade[i] = 'F';
    }
    cout << "\n--- Student Records ---" << endl;
    for(int i = 0; i < n; i++) {
        cout << "\nStudent " << i+1 << ":" << endl;
        cout << "Name: " << names[i] << endl;
        cout << "Roll No: " << rollNo[i] << endl;
        cout << "Total: " << total[i] << endl;
        cout << "Average: " << average[i] << endl;
        cout << "Grade: " << grade[i] << endl;
    }
    ofstream file("students.txt");
    for(int i = 0; i < n; i++) {
        file << names[i] << " << rollNo[i] << " << total[i] << " << average[i] << " << grade[i] << endl;
    }
    file.close();

    cout << "\nData saved in students.txt. Program ended." << endl;
    return 0;
}
