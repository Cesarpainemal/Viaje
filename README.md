# Viaje

package viaje;

import java.util.Scanner;

public class Viaje {

    public static void main(String[] args) {

		Scanner sc=new Scanner(System.in);
		
		System.out.print("¿Cuántos adultos viajarán? (mayores de 16 y menores de 65): ");
		int adultos=sc.nextInt();
		System.out.print("¿Cuántos adultos mayores viajarán? (mayores de 65): ");
		int adultosMay=sc.nextInt();
		System.out.print("¿Cuántos niños viajarán? (menores de 16): ");
		int ninos=sc.nextInt();
		System.out.print("¿Cuál es la distancia de su viaje? (en km): ");
		int dist=sc.nextInt();	
		
		Ventas viaje=new Ventas(adultos, adultosMay, ninos, dist);
		
		
		double total= viaje.Precio()-viaje.Descuento();
		
		System.out.println("\nEl valor total del viaje es $" + total);

		
	}

}

----------------------------------------------------------------------------

package viaje;

public class Ventas {
    private int niños;
    private int adultos;
    private int adultosMayores;
    private int distancia;
	
	
	public Ventas(int niños, int adultos, int adultosMayores, int distancia) {
		
		this.niños = niños;
		this.adultos = adultos;
		this.adultosMayores = adultosMayores;
		this.distancia = distancia;
	}
	
	
	
	public double Precio(){
		
		if(distancia>1030 && adultos>3){
			return (distancia*523*(niños+adultos+adultosMayores)*0.9)-(distancia*523*adultosMayores*0.25);
		}else if(adultos==2 && niños==1){
			return (distancia*523*3*0.92)-(distancia*523*adultosMayores*0.25);
		}else{
			return ((distancia*523)*(niños+adultos))+(distancia*523*adultosMayores*0.5);				
		}
		
	}
	
	
	public double Descuento(){
		
		if(Precio()>550000){
			return Precio()*0.2;
		}else{
			return 0;
		}
		
	}
	
	

}
    
