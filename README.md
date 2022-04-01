# labo.cpp
#include <iostream>
#include "biblioteca.hpp"
using namespace std;

int main() {
	int n1, n2, Residuo, Resultado;
	char Op;
	Op='a';
	while(Op!='0'){
		cout<<("\tCalculadora (Los numeros ingresados deben ser numeros positivos o **0**)\n");
		cout<<("1: Suma\n");
		cout<<("2: Resta\n");
	cout<<("3: Multiplicacion\n");
		cout<<("4:Division\n");
		cout<<("0:Salir\n");
		cout<<("Ingrese 2 numeros "); 
		cin>>(n1);
		 cin>>(n2);
		 cout<<("\n");
		cout<<("Ingrese la operacion que realizara: "); 
		cin>>Op;
		if(Op=='1'){
			Resultado=suma(n1, n2);
			cout<<("El resultado de la suma es: %d\n\n", Resultado);
		}
		else{
			if (Op=='2'){
				Resultado=resta(n1, n2);
				if (n2>n1) printf("WARNING: resultado sera un numero postivo, este es el valor absoluto de la resta \n");
				cout<<("El resultado de la resta es: %d\n\n", Resultado);	
			}
			else{
				if (Op=='3'){
					Resultado=multi(n1,n2);
					cout<<("El resultado de la multiplicacion es: %d\n\n", Resultado);	
				}
				else{
				if (Op=='4'){
					if(n2==0) cout<<("WARNING: La operacion Solicitada no sera admitida\n\n");
					else{
						Resultado=div(n1, n2);
						if(n1>=n2)Residuo=n1%n2;
						else Residuo=n2%n1;
						if(Residuo!=0){
							cout<<("WARNING: La division no sera exacta.\n");
							cout<<("Deseas continuar? S/N (El Resultado no incluira Numeros decimales ni se incluira el residuo): ");
							cin>>Op;
							if(Op=='S'||Op=='s') cout<<("El resultado de la division sera: %d \n\n", Resultado);
							if(Op=='N'||Op=='n') cout<<("\n\n");
						}
						else cout<<(" El resultado de la division sera:%d\n\n", Resultado);
						}
					}
				}
			}
		}
	}
	system("pause");

}
