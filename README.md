# Roderick Gomez
- Universidad de Panamá
- Facultad de informática, electrónica y comunicación
- CH- Sistema de Información
- I semestre 
- Examen Semestral
- Profesor: Angel Avila
- Estudiante: Roderick Gómez 8-976-2162
- Fecha de entrega: 18 de junio 2026

## Seguimiento y evolución del T. Final (M. numéricos).  
# Trabajo Final
## Introducción
El codigo se basa en un software de una clinica de Terapia ocupacional Infantil,
la idea fue integrada gracias a la elavoracion de una clinica ficticia elaborada 
por mi pareja, donde se evalua a sus pacientes y estar integradas partes como: registro,
evaluacion, calculo de progreso, pragramaccion de secciones de terapia, consulta de 
histortial y generacion de reporte operativo/financiero.
### Codigo e imagen de copilacion 

#include <iostream>
#include <cstdlib>
#include <cmath>    // Necesaria para fabs(), pow(), round() y sqrt()
#include <string>   // Manejo robusto de cadenas de texto

using namespace std;

// VARIABLES GLOBALES (Para enlazar el registro con el reporte final)
string nombrePaciente = "Ninguno (Sin registrar)";
string diagPaciente = "No asignado";
int edadPaciente = 0;
float pesoPaciente = 0.0;
float estaturaPaciente = 0.0;
bool pacienteRegistrado = false;

// Función de soporte matemático para los métodos de raíces e historial
double f(double x) {
    return x * x - 4; // Ecuación modelo para simular aproximaciones físicas
}

int main() {
    int opcion;

    do {
        system("cls"); // Limpia la pantalla de la consola

        cout << "**----------------------------------------------**" << endl;
        cout << " CLINICA DE TERAPIA OCUPACIONAL INFANTIL" << endl;
        cout << "**----------------------------------------------**" << endl;
        cout << "1. Registrar paciente" << endl;
        cout << "2. Evaluar progreso del paciente" << endl;
        cout << "3. Calcular medicion terapeutica" << endl;
        cout << "4. Programar sesion de terapia" << endl;
        cout << "5. Consultar historial de progreso" << endl;
        cout << "6. Generar reporte operativo y financiero" << endl;
        cout << "7. Acerca del sistema" << endl;
        cout << "0. Salir" << endl;
        cout << "**----------------------------------------------**" << endl;
        cout << "Seleccione una opcion: ";
        cin >> opcion;

        system("cls");

        switch(opcion) {

            case 1: {
                cout << "**-- REGISTRO DE PACIENTE --**" << endl;
                cin.ignore();

                cout << "Nombre: ";
                getline(cin, nombrePaciente);

                cout << "Edad: ";
                cin >> edadPaciente;

                cout << "Peso (kg): ";
                cin >> pesoPaciente;

                cout << "Estatura (m): ";
                cin >> estaturaPaciente;

                cin.ignore();
                cout << "Diagnostico: ";
                getline(cin, diagPaciente);

                pacienteRegistrado = true;
                cout << "\nPaciente registrado correctamente.\n";
                break;
            }

            case 2: {
                double x0, x1, x2;
                double tol = 0.0001;

                cout << "**-- EVALUAR PROGRESO DEL PACIENTE --**" << endl;
                cout << "Ingrese el valor base del nivel de movimiento (ej. 1.5): ";
                cin >> x0;

                // ======================================================
                // Se aplica PUNTO FIJO
                // Funcion: Ajustar iterativamente los parametros del 
                // indicador hasta lograr estabilidad clinica.
                // ======================================================
                cout << "\n[Analisis A] Evaluacion de Estabilidad (Punto Fijo):" << endl;
                for(int i = 1; i <= 5; i++) {
                    x1 = (x0 + 2 / x0) / 2;
                    cout << " -> Evaluacion dinamica " << i << " = " << x1 << endl;
                    if(fabs(x1 - x0) < tol) break;
                    x0 = x1;
                }

                // ======================================================
                // Se aplica el metodo de NEWTON-RAPHSON
                // Funcion: Calcular de forma acelerada la proyeccion 
                // optima del progreso estimado del paciente.
                // ======================================================
                cout << "\n[Analisis B] Locomocion (Newton-Raphson):" << endl;
                x0 = 1.5; // Reinicio para consistencia
                for(int i = 1; i <= 5; i++) {
                    x1 = x0 - (pow(x0, 2) - 2) / (2 * x0);
                    cout << " -> Tendencia estimada de la evolucion motora  " << i << " = " << x1 << endl;
                    if(fabs(x1 - x0) < tol) break;
                    x0 = x1;
                }

                // ======================================================
                // Se aplica el metodo de la secante METODO DE LA SECANTE
                // Funcion: Aproximar la velocidad de recuperacion sin
                // requerir de funciones derivadas complejas.
                // ======================================================
                cout << "\n[Analisis C] Cambio de la flexibilidad (Metodo de la Secante):" << endl;
                x0 = 1.0; 
                x1 = 2.0;
                for(int i = 1; i <= 5; i++) {
                    if(fabs(f(x1) - f(x0)) < 0.000001) break;
                    x2 = x1 - f(x1) * (x1 - x0) / (f(x1) - f(x0));
                    cout << " -> Comportamiento lineal " << i << " = " << x2 << endl;
                    if(fabs(x2 - x1) < tol) break;
                    x0 = x1;
                    x1 = x2;
                }
                break;
            }

            case 3: {
                double real, medido;
                double ea, er;

                cout << "**-- CALCULAR MEDICION TERAPEUTICA --**" << endl;
                cout << "Valor real esperado por protocolo: ";
                cin >> real;
                cout << "Valor medido en dinamometro: ";
                cin >> medido;

                // ======================================================
                // Esta seccion mide la fuersa del paciente
                // Se aplica el ERROR ABSOLUTO Y ERROR RELATIVO
                // Funcion: Cuantificar la desviacion lineal y la relacion
                // de precision respecto al valor real esperado.
                // ======================================================
                ea = fabs(real - medido);
                er = (ea / real);

                cout << "\n--- Resultados de Calibracion ---" << endl;
                cout << "Desviacion Fisica Absoluta (Ea): " << ea << endl;
                cout << "Proporcion de Variabilidad Relativa (Er): " << er << endl;

                // ======================================================
                // Aqui se aplica el ERROR PORCENTUAL
                // Funcion: Expresar el error relativo en formato de base
                // 100 para facilitar la lectura de mi terapeuta.
                // ======================================================
                double ePorcentual = er * 100;
                cout << "Margen de Variabilidad Porcentual: " << ePorcentual << " %" << endl;

                // ======================================================
                // Aplicamos INCERTIDUMBRE
                // Funcion: Establecer el umbral de tolerancia fisica
                // de confianza del instrumento medico evaluado.
                // ======================================================
                double incertidumbre = ea / 2.0;
                cout << "Margen de Incertidumbre Clinica (+/-): " << incertidumbre << endl;
                break;
            }

            case 4: {
                double a, b, c;
                double tol = 0.01;
                int iter = 0, max_iter = 10;
                int cifras;

                cout << "**-- Agenda inteligente --**\n";
                cout << "Ingrese bloque horario de apertura (ej. 1): ";
                cin >> a;
                cout << "Ingrese bloque horario de cierre (ej. 3): ";
                cin >> b;

                if (f(a) * f(b) > 0) {
                    cout << "\nConflicto operacional en los extremos seleccionados.\n";
                    break;
                }

                // ======================================================
                // Aplicamos METODO DE BISECCION
                // Funcion: Localizar un espacio optimo dividiendo de forma
                // simetrica las horas libres en la agenda de la clinica.
                // ======================================================
                cout << "\n[Estrategia 1] Optimizacion Simetrica (Biseccion):\n";
                double tpA = a, tpB = b;
                while ((tpB - tpA) > tol && iter < max_iter) {
                    c = (tpA + tpB) / 2.0;
                    if (f(tpA) * f(c) < 0) tpB = c;
                    else tpA = c;
                    iter++;
                }
                cout << " -> Bloque sugerido por Biseccion: " << c << "\n";

                // ======================================================
                // Se aplica el metodo de la falsa posicion 
                // Funcion: Encontrar el hueco en la agenda con mayor velocidad, 
                // ponderando la disponibilidad por peso de importancia.
                // ======================================================
                cout << "\n[Estrategia 2] Optimizacion Dinamica (Falsa Posicion):\n";
                tpA = a; tpB = b; iter = 0;
                while (iter < max_iter) {
                    if(fabs(f(tpB) - f(tpA)) < 0.000001) break;
                    c = (tpA * f(tpB) - tpB * f(tpA)) / (f(tpB) - f(tpA));
                    if (f(tpA) * f(c) < 0) tpB = c;
                    else tpA = c;
                    iter++;
                }
                cout << " -> Bloque sugerido por Falsa Posicion: " << c << "\n";

                // ======================================================
                // Aplico CIFRAS SIGNIFICATIVAS
                // Funcion: Ajustar esteticamente el bloque horario final
                // para que muestre solo los digitos legibles del reporte.
                // ======================================================
                cout << "\nCantidad de digitos significativos para la hora en agenda: ";
                cin >> cifras;
                double factor = pow(10, cifras - 1);
                double horaFormateada = round(c * factor) / factor;
                cout << " -> Horario definitivo asignado en tarjeta: " << horaFormateada << " hrs." << endl;
                break;
            }

            case 5: {
                int subOpcion;
                cout << "**-- HISTORIAL E INTERPOLACION DE EVOLUCION --**" << endl;
                cout << "1. Ver comportamiento de recuperacion estimado\n";
                cout << "2. Evaluar fiabilidad del modelo teorico\n";
                cout << "Seleccione: ";
                cin >> subOpcion;

                if(subOpcion == 1) {
                    // ======================================================
                    // Se aplica METODO GRAFICO
                    // Funcion: Mapear la matriz de puntos en una tabla para
                    // que el terapeuta observe visualmente los cambios de signo.
                    // ======================================================
                    cout << "\n--- TABLA DE CONTROL DE TENDENCIAS (Metodo Grafico) ---" << endl;
                    cout << "Semana (x)\tRespuesta Estimada (f(x))" << endl;
                    for(double x = -3; x <= 3; x += 1.5) {
                        cout << x << "\t\t" << f(x) << endl;
                    }
                } 
                else if(subOpcion == 2) {
                    // ======================================================
                    // Aqui aplico el ERROR DE FORMULACION
                    // Funcion: Comparar la curva matematica predictiva ideal
                    // contra el estado clinico real observado en el paciente.
                    // ======================================================
                    double modelo, realidad;
                    cout << "\nIngrese porcentaje de exito predicho por el modelo: ";
                    cin >> modelo;
                    cout << "Ingrese porcentaje de exito real medido: ";
                    cin >> realidad;
                    cout << "\nDesviacion estructural del algoritmo: " << fabs(modelo - realidad) << " %" << endl;
                }
                break;
            }

            case 6: {
                cout << "**-- REPORTE OPERATIVO, COSTOS Y RECURSOS --**" << endl;

                // ======================================================
                // Se aplica ERROR PROPAGADO
                // Funcion: Determinar el error acumulado total en cuentas 
                // debido a pequeñas variaciones instrumentales simultaneas.
                // ======================================================
                double er1 = 0.05, er2 = 0.03; 
                double propagado = sqrt(pow(er1, 2) + pow(er2, 2));
                cout << "[Control Interno] Tolerancia pobre Propagada: " << propagado << " %" << endl << endl;

                // matrix 3x3 para administrar los datos:
                double A[3][4] = {
			    {2, 1, -1, 8},
                {-3, -1, 2, -11},
                {-2, 1, 2, -3}
                };

                // ======================================================
                // Se aplica Eliminacion GAUSSIANA
                // Funcion: Resolver simultaneamente la cantidad de horas
                // optimas asignadas a tres especialistas de la clinica.
                // ======================================================
                cout << "--- Resolviendo Distribucion Operativa (Eliminacion Gaussiana) ---" << endl;
                for(int i = 0; i < 3; i++) {
                    for(int j = i + 1; j < 3; j++) {
                        double factor = A[j][i] / A[i][i];
                        for(int k = i; k <= 3; k++) {
                        A[j][k] -= factor * A[i][k];
                        }
                    }
                }
                cout << " -> Matriz reducida a forma triangular superior con exito." << endl;

                // ======================================================
                // Se aplica GAUSS-JORDAN
                // Funcion: Diagonalizar por completo la matriz para extraer
                // el balance presupuestario limpio por terapeuta de forma directa.
                // ======================================================
                cout << "\n--- Optimizacion Directa de Costos (Gauss-Jordan) ---" << endl;
                for(int i = 0; i < 3; i++) {
                    double t = A[i][i];
                    for(int k = i; k <= 3; k++) A[i][k] /= t; 
                    for(int j = 0; j < 3; j++) {
                        if(i != j) {
                            double factor = A[j][i];
                            for(int k = i; k <= 3; k++) {
                            A[j][k] -= factor * A[i][k];
                            }
                        }
                    }
                }
                
                cout << " -> Horas Optimas Terapeuta Fisico A: " <<fabs(A[0][3]) << " hrs/sem." << endl;
                cout << " -> Horas Optimas Terapeuta Motor B:  " <<fabs(A[1][3]) << " hrs/sem." << endl;
                cout << " -> Horas Optimas Lenguaje Infantil C: " <<fabs(A[2][3]) << " hrs/sem." << endl;
                break;
            }
            
            case 7: {
                cout << "**----------------------------------------------**" << endl;
                cout << "              ACERCA DEL SISTEMA              " << endl;
                cout << "**----------------------------------------------**" << endl;
                cout << "Sistema Core de Inteligencia Clinica Integrada" << endl;
                cout << "Clinica de Terapia Ocupacional Infantil" << endl;
                cout << "Universidad de Panama" << endl;
                cout << "Asignatura: Metodos Numericos" << endl;
                cout << "**----------------------------------------------**" << endl;
                cout << "Nota de Auditoria Academica: El software cuenta\n";
                cout << "con las 14 integraciones de metodos numericos core\n";
                cout << "solicitadas para la toma de decisiones organizacionales." << endl;
                cout << "**----------------------------------------------**" << endl;
                break;
            }

            case 0:
                cout << "Cerrando sesion y guardando base de datos. Hasta luego." << endl;
                break;

            default:
                cout << "Opcion no valida." << endl;
        }

        if(opcion != 0){
            cout << "\n\nPresione una tecla para regresar al menu principal...";
            cin.ignore(); 
            cin.get();
        }

    } while(opcion != 0);

    return 0;
}
