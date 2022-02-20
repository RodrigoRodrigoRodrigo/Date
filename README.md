package application;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.time.Instant;
import java.util.Calendar;
import java.util.Date;

public class Program {

	public static void main(String[] args) throws ParseException {
		
		SimpleDateFormat sdf = new SimpleDateFormat("dd/MM/yyyy HH:mm:ss");
		
		Date d = Date.from(Instant.parse("2018-06-25T15:42:07Z"));
		
		System.out.println(sdf.format(d));
		
		Calendar cal = Calendar.getInstance();
		cal.setTime(d);
		cal.add(Calendar.HOUR_OF_DAY, 4); // para acrescentar 4 horas, se quiser acrescentas ou tirar horas, apenas mude o numero 4.
		d = cal.getTime();
		
		System.out.println(sdf.format(d));
		
		System.out.println();
		System.out.println("---------------------------------------------------------------------------------------");
		System.out.println();
		
		int minutes = cal.get(Calendar.MINUTE); //para saber quantos minutos que tem a hora desta data.
		int month = cal.get(Calendar.MONTH); // para saber o mês desta data
		// se quiser saber o dia, mes, ano, horas, minutos e segundos, apenas mude o .MINUTE, ou .MONTH
		// depois do (Calendar.MINUTE/MONTH)
		
		System.out.println("Minutes: " + minutes);
		System.out.println("Month: " + month);
		
	}

}
[06-topicos-especiais.pdf](https://github.com/yarisb/Date/files/8104807/06-topicos-especiais.pdf)
