package application;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.time.Instant;
import java.util.Date;
import java.util.TimeZone;

public class Program {

	public static void main(String[] args) throws ParseException {
		
		// SimpleDateFormat define formatos para conversão entre Date e String
		SimpleDateFormat sdf1 = new SimpleDateFormat("dd/MM/yyyy");
		SimpleDateFormat sdf2 = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
		SimpleDateFormat sdf3 = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
		
		sdf3.setTimeZone(TimeZone.getTimeZone("GMT")); // para imprimir a data do formato UTC
		
		Date x1 = new Date(); // para chamar a data atual.
		Date x2 = new Date(System.currentTimeMillis()); // outra forma de chamar o horario de agora, atual, ele pega o instante do meu sistema, converte para milliSegundos e cria a data com esse valor.
		Date x3 = new Date(0L); // passando 0 milliSegundos, ele vai pra data armazenada do dia 1 de janeiro as 00:00 de 1970 de Greenwich GMT(UTC), porem imprimi quantas horas atrasado ou adiantado ou correto, dependendo de onde você está. 
		Date x4 = new Date(1000L * 60L * 60L * 5L); // correspondente a 5 horas da manha do dia 1 de janeiro as 00:00 de 1970
		//1 minuto tem mill milliSegundo, 1000L * 60L = da 1 minuto * 60L = pra dar 1 Hora, * 5L = pra dar 5 horas.
		
		Date y1 = sdf1.parse ("25/06/2018");
		Date y2 = sdf2.parse ("25/06/2018 15:42:07");
		
		Date y3 = Date.from(Instant.parse ("2018-06-25T15:42:07Z"));
		/* 
		 Diante disso, o JAVA8 em diante ele tem uma nova biblioteca para mexer com data, essa biblioteca tem varias
		 recursos e um deles é a classe Instant, essa classe Instant, ela ja tem uma funçãozinha que se chama .pase
		 EXEMPLO: "(Instant.parse());", se voce colocar dentro do parenteses um String entre " " no formato do ISO 8601
		 ele automaticamente ele pode convertido para o tipo Date do JAVA se voce colocar o Date.from, então
		 ficou muito pratico você instanciar um Date apartir de uma data do formato  ISO 8601, usando como auxiliar
		 a Classe Instant
		*/
		
		//----------------------------------------------------------------------------------------------------------//
		//por padrão as maquinas as datas são impressas no formato da maquina local, por exemplo brasil
		//ela imprimi com o horario de brasilia, ele ta imprimindo com 3 horas de atraso do UTC
		//----------------------------------------------------------------------------------------------------------//
		
		// FORMATO: "yyyy-MM-ddTHH:mm:ssZ
		// EXEMPLO: "2018-06-25T15:42:07Z"
		// padrão ISO 8601 ^ é um padão muito utilizado para se armazenar datas em forma de texto 
		// o Z no final corresponde ao formato UTC
		
		System.out.println("x1: " + x1);
		System.out.println("x2: " + x2);
		System.out.println("x3: " + x3);
		System.out.println("x4: " + x4);
		System.out.println("y1: " + y1);
		System.out.println("y2: " + y2);
		System.out.println("y3: " + y3);
		
		System.out.println("-------------");
		
		System.out.println("x1: " + sdf2.format(x1));
		System.out.println("x2: " + sdf2.format(x2));
		System.out.println("x3: " + sdf2.format(x3));
		System.out.println("x4: " + sdf2.format(x4));
		System.out.println("y1: " + sdf2.format(y1));
		System.out.println("y2: " + sdf2.format(y2));
		System.out.println("y3: " + sdf2.format(y3));
		
		System.out.println("-------------");
		
		System.out.println("x1: " + sdf3.format(x1));
		System.out.println("x2: " + sdf3.format(x2));
		System.out.println("x3: " + sdf3.format(x3));
		System.out.println("x4: " + sdf3.format(x4));
		System.out.println("y1: " + sdf3.format(y1));
		System.out.println("y2: " + sdf3.format(y2));
		System.out.println("y3: " + sdf3.format(y3));
	}

}
