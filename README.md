#include <iostream>
#include <string>
using namespace std;

string chiffrementCesar(const string& message, int decalage) {
   string resultat = "" ;
    for (char lettre : message) {
        if(isalpha(lettre)) {
            char base = (isupper(lettre)) ? 'A' : 'a';
            resultat += static_cast<char>((lettre-base+decalage)%26 +base);
        } else {
            resultat += lettre ;
        }
    }
    return resultat ;
}

int main() {
    string message ;
    int decalage ;
    int option;
    string messageChiffre;
    string messageDechiffre;

    cout << "Entrez le message : " ;
   getline(cin, message) ;

    do{
       cout << "1- Chiffrer le message"   << endl   << "2- Dechiffrer le message"   << endl ;
    cout << "Que voulez-vous faire? Choissisez une option " ;
       cin >> option ;
    }while(option < 1 || option > 2);

    do{
        cout << "Entrez le decalage : " ;
        cin >> decalage ;
      }while(decalage < 0 || option > 25);

    if(option==1){
        messageChiffre = chiffrementCesar(message, decalage) ;
        cout << "Message chiffre : "  << messageChiffre << endl ;
    }else if(option==2){
        messageDechiffre = chiffrementCesar(message, decalage*-1) ;
        cout << "Message dechiffre : "  << messageDechiffre << endl ;
    }
    return 0 ;
}


