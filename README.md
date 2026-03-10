# Oops-project-1
Question 1 – The Smart Thermostat (Boundary 
Validation)
#include<iostream>
#include<string>
using namespace std;
class Thermostat { private:
string roomName;
double temperature;
public:
Thermostat(string name, double temp) : roomName(name), temperature(temp) {
if (temp < 16.0 || temp > 30.0) temperature = 16.0; // default to min if invalid 
}
double getTemperature() { return temperature; }
void setTemperature(double temp) { 
if (temp >= 16.0 && temp <= 30.0) {
temperature = temp; 
} else {
cout << "Error: " << temp << "C is outside the hardware limits (16.0C - 30.0C)." << endl; 
}
}
};
int main() {
Thermostat t("Living Room", 22.5);t.setTemperature(35.0);
t.setTemperature(18.0);
cout << "Current Temp: " << t.getTemperature() << "C" << endl; 
return 0; 
}
Question 2 – The Digital Parking Meter (Capacity Capping)
#include<iostream>
using namespace std;
class ParkingMeter {
private:
int timeRemaining;
const int maxTime = 120;
public:
ParkingMeter() : timeRemaining(0) {}
int getTimeRemaining() { return timeRemaining; } 
void addTime(int minutes) { 
if (timeRemaining + minutes > maxTime) {
timeRemaining = maxTime;
cout << "Max time reached. Excess coins refunded." << endl;
} else {
timeRemaining += minutes;
} 
}
};
int main() { 
ParkingMeter meter;
meter.addTime(60); 
meter.addTime(90);
cout << "Time on meter: " << meter.getTimeRemaining() << " mins" << endl;
return 0; 
}slot.buySnack(3);
slot.buySnack(4);
cout << "Remaining Stock: " << slot.getStockQuantity() << endl;
return 0;
}
Question 4 – Secure UserProfile Class
#include<iostream>
#include<string>
using namespace std;
class UserProfile {
string username;
string password;
public:
// Constructor
UserProfile(string username, string password) : username(username), password(password) 
{}
// Getter
string getUsername() { return username; }
// Setter updatePassword
void updatePassword(string oldPassword, string newPassword) {
 if (password == oldPassword) {
 password = newPassword;
 cout << "Password updated." << endl;
 } else {
 cout << "Access Denied: Incorrect current password." << 
endl;
 }
}
};
// Example usage
int main() { 
UserProfile user("ali_dev", "qwerty123");
user.updatePassword("wrongpass", "newSecurePass!"); 
user.updatePassword("qwerty123", "newSecurePass!");
return 0;
}
Question 5 – GameCharacter Class
#include<iostream>
#include<string>
using namespace std;
class GameCharacter {
private:
string name;
int health;
int maxHealth;
public:
// Constructor
GameCharacter(string name, int health, int maxHealth) : name(name), health(health), 
maxHealth(maxHealth) 
{
clampHealth();
}
// Getters
string getName() { return name; }
int getHealth() { return health; }
int getMaxHealth() { return maxHealth; }
// Clamp health between 0 and maxHealth
void clampHealth() {
 health = max(0, min(health, maxHealth));
}
// Modify health and clamp
void changeHealth(int delta) {
 health += delta;
 clampHealth();
}
};
// Example usage int main() { 
GameCharacter player("Hero", 50, 100);
player.changeHealth(-60);
// health goes to 0 
cout << player.getHealth() << endl;
player.changeHealth(150);
 cout << player.getHealth() << endl; 
return 0;
}
Question 6 – LoyaltyCard class (C++)
#include <iostream>
#include <string>
using namespace std;
class LoyaltyCard {
private:
 string customerName;
 int stamps;
public:
 // Constructor
 LoyaltyCard(string customerName) {
 this->customerName = customerName;

this->stamps = 0;
 }
 // Getter
 int getStamps() { return stamps; }
 // Setter – addStamp
 void addStamp() {
 stamps++;
 if (stamps == 10) {
 cout << "Congratulations " << customerName << "! You earned a free coffee!" << 
endl;
 stamps = 0;
 }
 }
};
// Example usage
int main() {
 LoyaltyCard card("Sara");
 for (int i = 0; i < 10; i++) {
 card.addStamp();
 }
 cout << "Current Stamps: " << card.getStamps() << endl;
 return 0;
}
