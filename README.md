# Display-House-or-Art
// Michael Kokaly, 1/26/24
// This program outputs either a house or an orgianl piece of art based on the users selection.
// When it comes to the house that is outputted, it is made depending on the amount of floors the user asks for.
// For the original art design, if selected will output a piece of my own.

// What my original piece of art is supposed to output
//           *
//           *
//          ***
//         *****
//        *******
//       *********
//      ***********
//     *************
//    ***************
//   *****************
//  *******************
// *********************
//         |   |
//         |___|

#include <iostream>
#include <iomanip>

using namespace std;


int main() {
    int choice;
    int floors;
    // The menu output
    cout << "Program 1: House" << endl;
    cout << "Which option would you like?" << endl;
    cout << "1. Display house" << endl;
    cout << "2. Display original art" << endl;
    cout << "Your choice: ";
    cin >> choice;

    if (choice == 1) { //if they pick this choice they are looking at the picture of a house
        cout << "How many floors should the house have? ";
        cin >> floors;
        
        // width of the house
        int roofwidth = 7 + ((floors - 1) * 3);

        // Print top of roof
        cout << string(floors, ' ') << string(roofwidth, '_') << endl;

        // prints the slashes on the sides of the roof
        for (int width = 0; width < floors; width++) {
            int spaces = floors - width - 1;    // used to print the spaces that go before and after each slash
            cout << string(spaces, ' ') << '/';
            cout << string(roofwidth, ' ');
            cout << "\\" << endl;
            spaces -= 1;    // increments the spaces to create that diagonal effect
            roofwidth += 2;  
        }

        int counter = 1;
        while (counter < floors) { // used to add floors depending on the user's input
            counter++;
            // prints the walls and the tops of each windows for that level
            cout << "|   ";   
            for (int windowtops = 1; windowtops < floors; windowtops++){
                cout << "_    ";
            }
            cout << "_   |" << endl;


            // prints the row of windows
            cout << "| ";
            for (int windows = 0; windows < floors; windows++){
                cout <<  " |_| ";
            }
            cout << " |" << endl;

            //prints the walls for the floor with no windows or underscores
            cout << "|  ";
            for(int spaces = 0; spaces < floors; spaces++){
                cout << "     ";
            }
            cout << "|" << endl;
        }

        // used to print that final layer of the top of the windows
        cout << "|   ";
        for (int windowtops = 1; windowtops < floors; windowtops++) {
                cout << "_    ";
            }
            cout << "_   |" << endl;

        // prints the top half of the door and the rest of the windows besides it
        cout <<  "|  | ";
        for (int lastwindow = 1; lastwindow < floors; lastwindow++) {
            cout <<  "|  |_";
        }
        cout << "|  |" << endl;

        // prints the bottom of the door of the house and the end of the wall on the left side
        cout << "|  | |";
        for(int space = 1; space < floors; space++) {
            cout << "     ";
        }
        cout << "  |" << endl;
        
        // prints the bottom base of the house
        cout << "///";
            for(int space = 0; space < floors; space++){
                cout << "/////";
            }
            cout << "/" << endl;


    } else if (choice == 2) {   // if selected the original piece of art will be printed
        int spaces = 10;
        int stars = 1;
        cout << endl;

        // prints the star on top of the tree
        cout << "          *" << endl;
        
        // prints the tree itself and the spaces are used to create the descending affect
        while (spaces >= 0){
            cout << string(spaces, ' ');
            cout << string(stars, '*') << endl;
            spaces -= 1;
            stars += 2;
        }
        // prints the stump of the tree
        cout << "        |   |" << endl;
        cout << "        |___|" << endl;

    } else {
        cout << "Invalid choice" << endl; // if neither option 1 or 2 is selected, and invalid choice will appear.
    }
}   
