# candleshop
Welcome to the candle shop

// Dante Bonomini IN 200 C++
// Chapter #3

// Program set up
#include<iostream>
#include<string>
#include<chrono>
#include<thread>
#include<cstdlib>
#include<ctime>
#include<array>
using namespace std;

int main() {
	// declarations
	string startProg;
	string userCandle;
	string help;
	string dailySpecial;
	string c;
	string candle;


	// Seed random number generator
	srand(time(0));

	// Extra dialouge for needed fun
	cout << "[You walk into a store...]\n";
	this_thread::sleep_for(chrono::milliseconds(2000));
	cout << "Worker: Do you like candles?\n[Please enter Yes or No]\n>>";
	cin >> startProg;

	// Start or Kill Program
	if (startProg == "Yes") {
		cout << "Great, if you need help let me know!!\n";
		this_thread::sleep_for(chrono::milliseconds(1000));

		// Users favorite candle
		cout << "Worker: What is your favorite candle?\n";
		cin >> userCandle;
		cout << "Worker: That's a great candle, here I have something for you.\n";
		this_thread::sleep_for(chrono::milliseconds(1000));

		// setting max number of candes
		string candle[] = { "Pumpkin Waffles" , "Paradise Punch" , "Fresh Cut Frasier" , "Caramel Cinnamon Roll" , userCandle};

		const int maxCandle = 5;
		string inv[maxCandle];
		inv[0] = "Pumpkin Waffles";
		inv[1] = "Paradise Punch";
		inv[2] = "Fresh Cut Frasier";
		inv[3] = "Caramel Cinnamon Roll";
		inv[4] = userCandle;


		cout << "[The worker is impressed with your choice and gifts you a free candle]\n";
		this_thread::sleep_for(chrono::milliseconds(2000));

		// For loop to find gift candle
		for (string c = 0; c < maxCandle; c) {
			cout << "Worker: here is the " << inv[c] << "candle." << endl;
		}

		// more fun dialouge just cause why not?
		cout << "[Would you like to ask for help? Yes or No?]\n>>";
		cin >> help;
		if (help == "Yes") {
			cout << "[You ask worker for help...]\n";
			this_thread::sleep_for(chrono::milliseconds(1000));


			// Random Daily Special
			cout << "Worker: Would you like to hear today's special? Yes or No?\n";
			cin >> dailySpecial;

			if (dailySpecial == "Yes") {
				cout << "Our special today is " << candle[rand() % 5] << endl;
				this_thread::sleep_for(chrono::milliseconds(2000));
			}
			else {
				cout << "Oh, okay then.\n";
				this_thread::sleep_for(chrono::milliseconds(2000));
			}
			// List of in stock candles
			cout << "Worker: Here is a list of our current inventory: \n";
			this_thread::sleep_for(chrono::milliseconds(750));
			cout << "Pumpkin Waffles\nParadise Punch\nFresh Cut Frasier\nCaramel Cinnamon Roll\n" << userCandle << endl;
			this_thread::sleep_for(chrono::milliseconds(5000));
			cout << "Worker: If you need anything else please come back and see us sometime.";
			this_thread::sleep_for(chrono::milliseconds(3500));
		}
		else {
			cout << "Okay thank you for shopping here.\n";
			return 0;
		}
	}
	else if (startProg == "No") {
		cout << "Oh, sorry this isn't the place for you. Goodbye...\n";
		this_thread::sleep_for(chrono::milliseconds(2500));
	}
	else {
	cout << "Sorry, I don't understand, Please try again sometime...\n";
	this_thread::sleep_for(chrono::milliseconds(2500));

	}
	
}
