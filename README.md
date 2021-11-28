# Lecture-14-Arrays-Algorithm

STANDARD LIBRARY ARRAYS

SLIDE 2, Standard Library Array

    #include <iostream>
    #include <array>
    using namespace std;

    int main()
    {
        array <int, 5> myarray = { 9, 7, 5, 3, 1 };
    }
    
SLIDE 3, Standard Library Array Methods

    #include <iostream>
    #include <array>
    using namespace std;

    int main()
    {
        array <string, 4> arr = { "Mars Bar", "Snickers", "Bounty", "Wispa" };
        cout << arr.at(1) << endl; //returns value at index 1 e.g. snickers
        cout << arr[1] << endl; //does the same as the above

        cout << arr.front() << endl; //returns value at beginning of array (Mars Bar)
        cout << arr.back() << endl; //returns value at end of array (Wispa)


    //utilise a for loop to run through array
        for (int i = 0; i < arr.size(); i++) { //note use size() in condition
            cout << arr.at(i) << ", ";
        }
        cout << endl;
    }
    
ALGORITHM

SLIDE 6, Algorithm Sorting Example

    #include <iostream>
    #include <array>
    #include <algorithm>
    using namespace std;

    int main()
    {
        array <int, 5> numbers = { 33, 5, 7, 99, 83 };
        sort(numbers.begin(), numbers.end()); //call to sort here
        for (int num : numbers) {
            cout << num << " "; //output should be 5, 7, 33, 83, 99
        }
    }
    
SLIDE 7, Algorithm Example Sorting Largest to Smallest

    #include <iostream>
    #include <array>
    #include <algorithm>
    using namespace std;

    int main()
    {
        array <int, 5> numbers = { 33, 5, 7, 99, 83 };
        sort(numbers.begin(), numbers.end()); //call to sort here
        reverse(numbers.begin(), numbers.end());//call to reverse here
        for (int num : numbers) {
            cout << num << " "; //output should be 5, 7, 33, 83, 99
        }
    }
    
SLIDE 8, Rand Function

    #include <iostream>
    #include <algorithm>
    #include <array>
    using namespace std;

    int main()
    {
        //initializing array with size of 10
        int randomArry[10];
        for (int i = 0; i < 10; i++)
        {
            //rand is used to generate a random variable
            //using %50 to make sure number aren't too big
            randomArry[i] = rand() % 50;
            cout << randomArry[i] << endl;
        }
    }
    
EXERCISES

SLIDE 9, Exercise

    #include <iostream>
    #include <algorithm>
    #include <array>
    using namespace std;

    int main()
    {
        int randomArray[1000];
        int i = 0;
        for (int x = 0; x < 1000; x++) { ////initializing array with size of 1000 random numbers
            randomArray[x] = rand() % 100; //between 1-100
            if (randomArray[x] == 6) { //counts the number 6 appears in the array
                cout << randomArray[x] << endl;
                i++;
            }
            else {
                continue;
            }
        }
        cout << "\nThe number 6 appeared " << i << " times"; //outputs the information to the console
    }
    
SLIDE 10, Exercise

    #include <iostream>
    #include <algorithm>
    #include <array>
    using namespace std;

    int main()
    {
        //variables
        int i;
        float arr[10];

        for (i = 0; i < 10; ++i) //ineteger array of 10 numbers
        {
            cout << "Enter number " << i + 1 << " : ";
            cin >> arr[i];
            while (cin.fail()) {
                cout << "Invalid input. Please enter a number:";
                cin.clear();
                cin.ignore(1000, '\n');
                cin >> arr[i];
            }
        }

        for (i = 1; i < 10; ++i)
        {
            if (arr[0] < arr[i])
                arr[0] = arr[i];
        }
        cout << "Largest element = " << arr[0];

        return 0;
    }
