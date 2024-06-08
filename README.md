#include<math.h>
#include<iostream>
#include<locale.h>
using namespace std;

int main()
{
setlocale(LC_ALL,"Spanish");
	// DECLARACION DE CONSTANTES Y VARIABLES
	float a, ma, vls, vst, n, ph, h;//es el factor theta
	int option;
	float pesom;//peso molecular
    char
	// pm=peso molecular, vsl=volumen de solucion, vst=volumen de soluto, a=tetha
	do {
		cout << "1. Calculadora de normalidad" << endl;
		cout << "2. Calculadora de molalidad" << endl;
		cout << "3. Calculadora de pH" << endl;
		cout << "4. Salir"<<endl;
		cout << "======================================================" << endl;
		cout << " Ingrese una opcion" << endl;
		cin >> option;
		switch (option) {
		case 1 :
		    cout << ""<<endl;
			cout << " NORMALIDAD = (m*a)/(pm*vsl)" << endl;
			cout << "ingrese su valor de masa" << endl;
			cin >> ma;
			while (ma<0){
                cout<<" La masa no puede ser negativa"<<endl;
                cin>>ma;
			}
			cout << " ingrese su valor de tetha" << endl;
			cin >> a;
			while(a<0){
                cout<< "El factor tetha debe ser mayor a 0"<<endl;
                cin>>a;
			}
			cout << "ingrese su valor de peso molecular" << endl;
			cin >> pesom;
			while (pesom==0) {
				cout << " No existen divisiones para 0" << endl;
				cin >> pesom;
			}
			cout << "ingrese su volumen de solucion" << endl;
			cin >> vls;
			while (vls<0 || vls==0) {
				cout << " No existen divisiones para 0, ni volumenes negativos" << endl;
				cin >> vls;
			}
           n= ma*a/(pesom*vls);

            cout<<" su normalidad es de: "<< n <<endl;
			break;
        case 2:
            cout<< " Molalidad = moles de soluto/ kg de disolvente"<<endl;



        break;
        case 3:
            cout<<" Calculadora de pH"<<endl;
            cout<<" Ingrese  la concentración de iones de hidrógeno en la solución, medida en mol/L"<<endl;
            cin>>h;
            while (h<=0){
                cout<<"No existen concentraciones de iones negativos"<<endl;
                cin>>h;
            }
            ph=-log10(h);
            cout<<" El pH de su solucion es:"<<ph<<endl;
            if(ph>14){
                cout<<" No hay pH's mayores a 14"<<endl;
            }else if(ph<0){
                cout<<"El pH no puede ser negativo"<<endl;
            }else if(ph<7){
                cout<<"Usted tiene una solucion acida"<<endl;
            }else if(ph>7){
                cout<<"Usted tiene una solucion alcalina o basica"<<endl;
            }else if(ph=7){
                cout<<"Usted tiene una solucion neutra"<<endl;
            }
        break;
        case 4:
            cout<<" Usted ha salido del programa con exito"<<endl;
            break;
        default:
            cout<<" Esta opcion es incorrecta, intente de nuevo"<<endl;
            break;
		}
	} while (option!=4);
	return 0;
}
