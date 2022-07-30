#include <iostream>
#include <string>
#include <array>

using namespace std;

#define string std::string
#define print std::cout
#define input std::cin
#define endl std::endl

class LoginManager {
public:
	string InputUsername;
	string InputPassword;
	int i{};

	void signup() {
		if (DatabaseSize < 5) {
			Usernames[DatabaseSize] = InputUsername;
			Passwords[DatabaseSize] = InputPassword;
			DatabaseSize++;
			print << "Registered, try logging in!" << endl;
			login();
		}
		else {
			print << "Error: Database full, try again later!" << endl;
			return;
		}

	}

	void login() {
		print << "Please enter a username." << endl;
		input >> InputUsername;

		for (i = 0; (i < DatabaseSize); i++) {
			if (InputUsername == Usernames[i]) {
				print << "Username found! Enter your password." << endl;
				input >> InputPassword;

				if (InputPassword == Passwords[i]) {
					print << "Logged in" << endl;
					return;
				}
				else {
					print << "Incorrect Password, try logging in again." << endl;
					login();
				}
			}
		}
		print << "Username not found, but registered! Signing up? Enter a password!" << endl;
		input >> InputPassword;
		signup();
	}
private:
	int DatabaseSize = 1;
	std::array<string, 5> Usernames = { "Pyro", "Gamezine" };
	std::array<string, 5> Passwords = { "Swag", "Coins" };
};

int main() {
	LoginManager Login;

	Login.login();
}
