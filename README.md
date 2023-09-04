
#principal
public class Principal {

	public static void main(String[] args) {
		Constructor micons=new Constructor();
	}

}



#constructor

import javax.swing.JOptionPane;

public class Constructor {

public Constructor() {
	proceso miproceso = new proceso();
	procesoDos miDos=new  procesoDos();
	 Object desicion;
	 String renombrar;
	 do {
	 desicion = JOptionPane.showInputDialog(null,"Desea.. ","Plan de trabajo",JOptionPane.QUESTION_MESSAGE,null,new Object[] {"Seleccione","Bloque-A","Bloque-B","Salir"},"Seleccione");
	 renombrar=String.valueOf(desicion);
	 switch (renombrar) {
	case "Bloque-A":
		miproceso.inicar();
		break;
	case "Bloque-B":
		miDos.iniciarDos();
		break;
	case "Salir":
		JOptionPane.showMessageDialog(null, "Gracias por usar el programa");
		break;
	default:
		break;
	}
		} while (renombrar!="Salir");
	 
}



}




# proceso1

import javax.swing.JOptionPane;
public class proceso {
	Object actividad;
	String actividadDos,resp;
	public void inicar() {
		do {
			 actividad =JOptionPane.showInputDialog(null,"Ejercicios Practicos","TALLER #1", JOptionPane.QUESTION_MESSAGE,null,new Object[] {"Seleccione Uno","#1","#2","#3","#4","#5","Salir"},"Seleccione Uno");
			 actividadDos=String.valueOf(actividad);
		switch (actividadDos) {
		case "#1":
			numeroUno();
			break;
		case "#2":
			Integer numero=Integer.parseInt(JOptionPane.showInputDialog("Ingrese un numero"));
			numeroDos(numero);
			break;
		case "#3":
			System.out.println("El numero es: "+ numeroTres());
			break;
		case "#4":
			Integer cantidad=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el tamaño del arreglo"));
			System.out.println("El numero mayor es: "+numeroCuatro(cantidad));
			break;
		case "#5":
			Integer tamaño=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el tamaño del arreglo 1 y 2"));
			System.out.println( numeroCinco(tamaño));
			break;
			
		case "Salir":

			break;
		default:
			break;
		}
		} while (actividadDos!="Salir");
	}

	private Integer numeroCinco(Integer tama) {
		int array1[]=new int [tama];
		int array2[]=new int [tama];
		int acumuladora=0;
		for (int i = 0; i < tama; i++) {
			array1[i]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el "+(i+1)+" del primer arreglo"));
			array2[i]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el "+(i+1)+" del segundo arreglo"));
			for (int j = 0; j < tama; j++) {
				acumuladora=array1[i]+array2[i];
			}
			System.out.println( "La suma del arreglo "+i+" es: "+acumuladora);
		}
		
		return null;
	}

	private Integer numeroCuatro(Integer cantidad) {
		Integer arreglo[]=new Integer [cantidad];
		for (int i = 0; i < cantidad; i++) {
			arreglo[i]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el numero "+(i+1)));
		}
		Integer numeroMayor=arreglo[0];
		for (int i = 0; i < arreglo.length; i++) {
			if (arreglo[i]>numeroMayor) {
				numeroMayor=arreglo[i];
			}
		}
		return numeroMayor;
	}

	private int numeroTres() {
		int n = (int) (Math.random() * (1 - 100)) + 100;
		return n;
	}

	private void numeroDos(Integer numero) {
		if (numero>10) 
			JOptionPane.showMessageDialog(null, "El numero "+numero+" es mayor a 10","INFORMACION",JOptionPane.INFORMATION_MESSAGE);
		else
			JOptionPane.showMessageDialog(null, "El numero "+numero+" es menor a 10","INFORMACION",JOptionPane.INFORMATION_MESSAGE);
	}

	private void numeroUno() {
		System.out.println("Ingreso de nombre");
		System.out.println(JOptionPane.showInputDialog("Ingrese su nombre Completo"));
	}
}


#proceso2
import java.sql.Array;
import java.util.ArrayList;
import java.util.HashMap;
import java.util.Hashtable;
import java.util.Iterator;
import java.util.List;
import java.util.Map;

import javax.swing.JOptionPane;
import javax.swing.plaf.synth.SynthOptionPaneUI;

public class procesoDos {
	Object taller1;
	String tallerDos;
	public void iniciarDos() {
		do {
			 taller1 =JOptionPane.showInputDialog(null,"Ejercicios Practicos","TALLER #2", JOptionPane.QUESTION_MESSAGE,null,new Object[] {"Seleccione Uno","#1","#2","#3","#4","#5","#6","#7","#8","Salir"},"Seleccione Uno");
			 tallerDos=String.valueOf(taller1);
		switch (tallerDos) {
		case "#1":
			numeroUno();
			break;
		case "#2":
			Integer numero=Integer.parseInt(JOptionPane.showInputDialog("Ingrese un numero"));
			numeroDos(numero);
			break;
		case "#3":
			System.out.println("El numero es: "+ numeroTres());
			break;
		case "#4":
			Integer cantidad=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el tamaño del arreglo"));
			System.out.println("El numero mayor es: "+numeroCuatro(cantidad));
			break;
		case "#5":
			Integer cantidades=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el tamaño del arreglo"));
			System.out.println("El numero mayor es: "+numeroCinco(cantidades));
			break;
		case "#6":
			Integer tamaño=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el tamaño del arreglo 1 y 2"));
			System.out.println( numeroSeis(tamaño));
			break;
		case "#7":
			String palabra=JOptionPane.showInputDialog("Ingrese la palabra la cual desea buscar");
			System.out.println(numeroSiete(palabra));
			break;
		case "#8":
			Integer numeros=Integer.parseInt(JOptionPane.showInputDialog("Cuantos estudiantes desea registrar"));
			System.out.println(numeroOcho(numeros));
			break;
		case "Salir":
			break;
		default:
			break;
		}
		} while (tallerDos!="Salir");
	}

	private String numeroOcho(Integer numeroso) {
		String nombres,pedido,cadena="",todos;
		Float calificaciones;
		Integer cantidadNotas;
		ArrayList<String>estudiantes=new ArrayList<>();
		Map<String, List<Float>> notasDeTodos=new HashMap<>();
		List<Float> notasEstudiantes = null;
		for (int i = 0; i < numeroso; i++) {
			nombres=JOptionPane.showInputDialog("Ingrese el nombre del estudiante "+(i+1));
			cantidadNotas=Integer.parseInt(JOptionPane.showInputDialog("Cuantas notas son las del estudiante "+nombres));
			estudiantes.add(nombres);
			notasEstudiantes=new ArrayList<>();
			for (int j = 0; j < cantidadNotas; j++) {
				calificaciones=Float.parseFloat(JOptionPane.showInputDialog("Ingrese la nota #"+(j+1)));
				notasEstudiantes.add(new Float(calificaciones) );
			}
			notasDeTodos.put(nombres, notasEstudiantes);
		}
		Object pedidos=JOptionPane.showInputDialog(null,"Desea ver las notas de algun estudiante","Anexo",JOptionPane.QUESTION_MESSAGE,null, new Object[] {"Seleccione","Si","No"},"Seleccione");
		pedido=String.valueOf(pedidos);
		switch (pedido) {
		case "Si":
			todos=JOptionPane.showInputDialog("Ingrese el nombre del estudiante");
			if (notasDeTodos.containsKey(todos)) {
				cadena="El estudiante "+todos+" y sus notas son: "+notasDeTodos.get(todos);

			}else 
				JOptionPane.showMessageDialog(null, "El estudiante "+todos+" no esta registrado") ;
			break;
		case "No":
			JOptionPane.showMessageDialog(null, "Gracias");
			break;
		default:
			break;
		}
		return cadena;
		
		
	}

	private String numeroSiete(String palabra) {
		Hashtable<String, String> diccionario = new Hashtable<String, String>();
		String cadena="";
		String valor;
		//
		diccionario.put("Apple", "Manzana");
		diccionario.put("Animal", "Animal");
		diccionario.put("Airplane", "Avión");
		diccionario.put("America" , "América");
		diccionario.put("Artist", "Artista");
		diccionario.put("Alligator", "Caimán");
		diccionario.put("Apartment", "Apartamento");
		diccionario.put("Alone", "Solo");
		diccionario.put("Answer", "Respuesta");
		diccionario.put("Ant", "Hormiga");
		//
		diccionario.put("Baby", "Bebé");
		diccionario.put("Banana", "Plátano");
		diccionario.put("Book", "Libro");
		diccionario.put("Bicycle" , "Bicicleta");
		diccionario.put("Beach", "Playa");
		diccionario.put("Brother", "Hermano");
		diccionario.put("Beautiful", "Hermoso/a");
		diccionario.put("Bag", "Bolsa");
		diccionario.put("Breakfast", "Desayuno");
		diccionario.put("Butterfly", "Mariposa");
		//
		diccionario.put("Cat", "Gato");
		diccionario.put("Car", "Coche");
		diccionario.put("Chocolate", "Chocolate");
		diccionario.put("Computer" , "Computadora");
		diccionario.put("Coffee", "Café");
		diccionario.put("City", "Ciudad");
		diccionario.put("Child", "Niño/a");
		diccionario.put("Camera", "Cámara");
		diccionario.put("Cloud", "Nube");
		diccionario.put("Cake", "Pastel");
		//
		diccionario.put("Dog", "Perro");
		diccionario.put("Day", "Día");
		diccionario.put("Dance", "Bailar");
		diccionario.put("Dream" , "Sueño");
		diccionario.put("Diamond", "Diamante");
		diccionario.put("Duck", "Pato");
		diccionario.put("Delicious", "Delicioso/a");
		diccionario.put("Door", "Puerta");
		diccionario.put("Doctor", "Doctor/a");
		diccionario.put("Dark", "Oscuro/a");
		if (diccionario.containsKey(palabra)) {
			cadena+="Ingles: "+palabra+"\nEspañol: "+diccionario.get(palabra);
		}else 
			JOptionPane.showMessageDialog(null, "La palabra no exisite en el diccionario","INFORMATION",JOptionPane.INFORMATION_MESSAGE);
		
			return cadena;
	}

	private Integer numeroSeis(Integer tama) {
		int array[]=new int [tama];
		int array2[]=new int [tama];
		int acumuladora=0;
		for (int i = 0; i < tama; i++) {
			array[i]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el "+(i+1)+" del primer arreglo"));
			array2[i]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el "+(i+1)+" del segundo arreglo"));
			for (int j = 0; j < tama; j++) {
				acumuladora=array[i]+array2[i];
			}
			System.out.println( "La suma del arreglo "+i+" es: "+acumuladora);
		}
		
		return null;
	}			
	private Integer numeroCinco(Integer cantidades) {
		ArrayList<Integer> array = new ArrayList<Integer>();
		for (int i = 0; i < cantidades; i++) {
			Integer arreglo=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el numero "+(i+1)));
			array.add(arreglo);
		}
		String sino=JOptionPane.showInputDialog(null, "Desea agregar un numero mas? \n Si= 1 \n No= 2");
		switch (sino) {
		case "1":
			Integer arreglo2=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el numero "));
			array.add(arreglo2);
			break;
		case "2":
			break;
		default:
			JOptionPane.showMessageDialog(null, "Dato ingresado invalido","ERROR",JOptionPane.ERROR_MESSAGE);
			break;
		}
		Integer numeroMayor=array.get(0);
		for (int i = 0; i < array.size(); i++) {
			if (array.get(i)>numeroMayor) {
				numeroMayor=array.get(i) ;
			}
		}
		return numeroMayor;
	}

	private Integer numeroCuatro(Integer cantidad) {
		Integer arreglo[]=new Integer [cantidad];
		for (int i = 0; i < cantidad; i++) {
			arreglo[i]=Integer.parseInt(JOptionPane.showInputDialog("Ingrese el numero "+(i+1)));
		}
		Integer numeroMayor=arreglo[0];
		for (int i = 0; i < arreglo.length; i++) {
			if (arreglo[i]>numeroMayor) {
				numeroMayor=arreglo[i];
			}
		}
		return numeroMayor;
	}

	private int numeroTres() {
		int n = (int) (Math.random() * (1 - 100)) + 100;
		return n;
	}

	private void numeroDos(Integer numero) {
		if (numero>10) 
			JOptionPane.showMessageDialog(null, "El numero "+numero+" es mayor a 10","INFORMACION",JOptionPane.INFORMATION_MESSAGE);
		else
			JOptionPane.showMessageDialog(null, "El numero "+numero+" es menor a 10","INFORMACION",JOptionPane.INFORMATION_MESSAGE);
	}

	private void numeroUno() {
		System.out.println("Ingreso de nombre");
		System.out.println(JOptionPane.showInputDialog("Ingrese su nombre Completo"));
	}
}











#teoria
1. Que es un método en java
Es un conjunto de instrucciones definidas dentro de una clase que realizan una determinada tarea y a las que podemos invocar mediante un nombre

2. ¿Cuáles son los cuatro tipos de métodos en Java?
Hay cuatros tipos n la cual se puede hacer:
1 con Retorno sin parámetro
2 sin Retorno con parámetro
3 con Retorno con parámetro
4 sin Retorno sin parámetro

3. ¿Cuál es la diferencia entre un método con parámetros y sin retorno y un método sin parámetro y con retorno?
El método sin retorno, pero con parámetros recibe una información externa al proceso mas no retorna un dato de vuelta si no que realiza el proceso interno y si necesita enviar algo lo hace directamente desde adentro como un print pero no en manera de retorno. Mientras que el método sin parámetro, pero con retorno usa variables internas ya sea pidiéndolas desde dentro o de alguna otra forma, pero en este caso si retorna algo fuera del proceso ya sea para ser almacenado de manera global o para ser usado en algún otro lugar del programa.
4. ¿Cuál es la diferencia entre un método con parámetros y con retorno y un método con parámetros y sin retorno?
Un método con parámetros y con retorno recibe información externa y realiza un proceso interno para retornar una información requerida en otro lugar del programa, mientras que el método con parámetros y sin retorno recibe la información, hace el proceso pero el resultado no se retorna de manera que no puede ser usado de manera externa en el programa si no que debe ser mostrado desde dentro del proceso.
5. ¿Por qué son importantes los métodos en Java?
Los métodos permiten realizar tareas repetitivas y almacenar este proceso en una clase y de esta manera si debe ser realizado x cantidad de veces nos ahorraremos código al solo tener que llamar al método y este repetirá el trabajo, así como que da un cierto orden a nuestro programa ya que este puede ser posicionado donde se quiera y ser llamado cuando se necesite.
6. ¿Qué es una estructura de datos?
es una colección de “valores”, de tipos de datos que se almacenan y organizan de tal forma que permiten un acceso y una modificación eficientes.

7. ¿Cuál es la diferencia entre un arreglo, un arrayList y un HashMap?
ArrayList mantiene el orden de inserción, mientras que HashMap no mantiene el orden de inserción, lo que significa que ArrayList devuelve los elementos de la lista en el mismo orden, mientras que HashMap no mantiene ningún orden, por lo que devuelve pares clave-valor en cualquier tipo de orden.

