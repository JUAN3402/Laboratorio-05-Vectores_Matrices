#include <iostream>
#include <cstdlib>
#include <ctime>
using namespace std;
int main(){
/*Crear una matriz cuadrada de números enteros de FxC.  Siendo F y C declaradas como constantes.
Calcular:
- ingrsar numeros random del 0 al 100
- Promedio general de la matriz.
- Suma de pares de cada columna
- Suma de impares de cada fila
- Posición máximo
- Posición mínimo
- Ordenar de forma ascendente la fila 2
- Ordenar en forma descendente la columna 3
- Intercambiar la 2 y 4 columna*/
const int F=4, C=4;
int matriz[F][C];
int suma=0;
int promedio=0;
int suma_pares=0;
int suma_impares=0;
int maximo=0;
int minimo=100;
int posicion_max[2];
int posicion_min[2];
int ayudin_vector[F];
int ayudin=0;
srand(time(0));
for(int i=0; i<F; i++){
for(int j=0; j<C; j++){
//- ingresar numeros random del 0 al 100 y mostrarlos
matriz[i][j]=rand()%101;
cout<<matriz[i][j]<<" ";
//- Promedio general de la matriz.
suma=suma+matriz[i][j];
promedio=suma/16;
//- Posición máximo
if(matriz[i][j]>maximo){
maximo=matriz[i][j];
posicion_max[0]=i+1;
posicion_max[1]=j+1;
}
//- Posición mínimo
if(matriz[i][j]<minimo){
minimo=matriz[i][j];
posicion_min[0]=i+1;
posicion_min[1]=j+1;
}
}
cout<<endl;
}
cout<<"Promedio general de la matriz: "<<promedio<<endl;
cout<<"Posicion maximo: columna:"<< posicion_max[1]<<", fila:"<<posicion_max[0]<<", contiene el numero:"<<maximo<<endl;
cout<<"Posicion minimo: columna:"<< posicion_min[1]<<", fila:"<<posicion_min[0]<<", contiene el numero:"<<minimo<<endl;
//- suma de pares de cada columna
cout<<"--Suma de pares de cada columna--"<<endl;
for(int i=0; i<F; i++){
for(int j=0; j<C; j++){
if(matriz[j][i]%2==0){
suma_pares=suma_pares+matriz[j][i];
}
}
cout<<"Columna"<<i+1<<": "<<suma_pares<<endl;
suma_pares=0;
}
//- suma de impares de cada fila
cout<<"--Suma de impares de cada fila--"<<endl;
for(int i=0; i<F; i++){
for(int j=0; j<C; j++){
if(matriz[i][j]%2!=0){
suma_impares=suma_impares+matriz[i][j];
}
}
cout<<"Fila"<<i+1<<": "<<suma_impares<<endl;
suma_impares=0;
}
//- Ordenar de forma ascendente la fila 2
cout<<"--Ordenar de forma ascendente la fila 2--"<<endl;
cout<<"Matriz antes: "<<endl;
for(int i=0;i<F;i++){
for(int j=0;j<C;j++){
cout<<matriz[i][j]<<" ";
}
cout<<endl;
}
for(int i=0;i<C;i++){
for(int j=i+1;j<F;j++){
if(matriz[1][i]<matriz[1][j]){
ayudin=matriz[1][i];
matriz[1][i]=matriz[1][j];
matriz[1][j]=ayudin;
}
}
}
cout<<"Matriz despues: "<<endl;
for(int i=0;i<F;i++){
for(int j=0;j<C;j++){
cout<<matriz[i][j]<<" ";
}
cout<<endl;
}
cout<<endl;
//- Ordenar en forma descendente la columna 3
cout<<"--Ordenar en forma descendente la columna 3--"<<endl;
cout<<"Matriz antes: "<<endl;
for(int i=0;i<F;i++){
for(int j=0;j<C;j++){
cout<<matriz[i][j]<<" ";
}
cout<<endl;
}
for(int i=0;i<F;i++){
for(int j=i+1;j<C;j++){
if(matriz[i][3]<matriz[j][3]){
ayudin=matriz[i][3];
matriz[i][3]=matriz[j][3];
matriz[j][3]=ayudin;
}
}
}
cout<<"Matriz despues: "<<endl;
for(int i=0;i<F;i++){
for(int j=0;j<C;j++){
cout<<matriz[i][j]<<" ";
}
cout<<endl;
}
//- Intercambiar la 2 y 4 columna
cout<<"--Intercambiar la 2 y 4 columna--"<<endl;
cout<<"Matriz antes: "<<endl;
for(int i=0;i<F;i++){
for(int j=0;j<C;j++){
cout<<matriz[i][j]<<" ";
}
cout<<endl;
}
for(int i = 0; i < C; i++) {
ayudin_vector[i] = matriz[i][1];
}
for(int i = 0; i < C; i++) {
matriz[i][1]=matriz[i][3];
}
for(int i = 0; i < C; i++) {
matriz[i][3]=ayudin_vector[i];
}
cout<<"Matriz despues: "<<endl;
for(int i=0;i<F;i++){
for(int j=0;j<C;j++){
cout<<matriz[i][j]<<" ";
}
cout<<endl;
}
}
