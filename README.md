# C-task-3
#include <iostream>
#include <vector>
using namespace std;

int main() {
    vector<string> tasks;
    int choice, taskNumber;
    string task;

    do {
        cout << "To-Do List"<<endl<<"Add"<<endl<<" View  "<<endl<<"delete"<<endl<<" Exit"<<endl<<"Enter your choice:"<<endl;
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter the task: ";
                cin.ignore();
                getline(cin, task);
                tasks.push_back(task);
                cout << "Task added"<<endl;
                break;
            case 2:
                if (tasks.empty()) {
                    cout << "No tasks yet"<<endl;
                } else {
                    cout <<"TASK"<<endl;
                    for (int i = 0; i < tasks.size(); i++) {
                        cout << i + 1 << ". " << tasks[i] << endl;
                    }
                }
                break;
            case 3:
                if (tasks.empty()) {
                    cout << "No tasks to delete"<<endl;
                } else {
                    cout << "Enter the task you want to delete";
                    cin >> taskNumber;
                    if (taskNumber > 0 && taskNumber <= tasks.size()) {
                        tasks.erase(tasks.begin() + taskNumber - 1);
                        cout << "Task deleted"<<endl;
                    } else {
                        cout << "Invalid"<<endl;
                    }
                }
                break;
            case 4:
                cout << "bye"<<endl;;
                break;
            default:
                cout << "enter a valid choice"<<endl;;
        }

    } while (choice != 4);

    return 0;
}
