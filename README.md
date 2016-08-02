# proyectpprogra1
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package proyectoprograjose;

/**
 *
 * @author Javier
 */

import javax.swing.JOptionPane;
import java.awt.Checkbox;
import java.awt.FlowLayout;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import javax.swing.JButton;
import javax.swing.JFrame;
import java.util.Date;
import java.text.SimpleDateFormat;
import java.text.DateFormat;

public class ProyectoPrograJose extends JFrame  {

    /**
     * @param args the command line arguments
     */
    static int camposVIP_A = 0;
    static double precioVIP_A = 0;
    static int camposVIP_B = 0;
    static double precioVIP_B = 0;
    static int camposPlateaPreferencia_A = 0;
     static double precioPlateaPreferencia_A = 0;
    static int camposPlateaPreferencia_B = 0;
    static double precioPlateaPreferencia_B = 0;
    static int camposGeneralEste = 0;
    static double precioGeneralEste = 0;
    static int camposGeneralOeste = 0;
    static double precioGeneralOeste = 0;
    static int camposGeneralNorte = 0;
    static double precioGeneralNorte = 0;
    static double TotalPagarCampos = 0; // total a pagar por  los campos
    static double Total_A_Apagar = 0;// total a pagar
    static double Impuesto = 0;// impuesto 0.13
    static double ImpuestoVIPA = 0; // acumulador impuesto VIP A
    static double ImpuestoVIPB = 0;// acumulador impuesto VIP B
        static double ImpuestoPreferencialA = 0;// acumulador impuesto Platea Preferencia A
        static double ImpuestoPreferencialB = 0; // Acumulador impuesto Platea Preferencial B
        static double ImpuestoGeneralNorte = 0; // acumulador impuesto General Norte
        static double ImpuestoGeneralEste = 0;// acumuador impuesto General Este
        static double ImpuestoGeneralOeste = 0;// acumulador impuesto General Oeste
        static int counter = 1; // Contador de entradas totales
        static int VIPA = 0;// contador entradas VIP A
        static int VIPB = 0;// Contador entradas VIP B
        static int PreferencialA = 0;// contador entradas Preferencial A
        static int PreferencialB = 0;// contador entradas Preferencial B
        static int GeneralEste = 0;// Contador entradas General Este
        static int GeneralOeste = 0;// Contador entradas General Oeste
        static int GeneralNorte = 0;// contador entradas General Norte
        static double TotalAPagarVIPA = 0;// acumulador del total pagado VIP A
        static double TotalAPagarVIPB = 0;// acumulador del total pagado VIP B
        static double TotalAPagarPreferencialA = 0;// acumulador del total pagado Preferencial A
        static double TotalAPagarPreferencialB = 0;// acumulador del total pagador Preferencial B
        static double TotalAPagarGeneralEste = 0;// acumulador del total pagado General Este
        static double TotalAPagarGeneralOeste = 0;// acumulador del total pagado General Oeste
        static double TotalAPagarGeneralNorte = 0;// acumulador del total pagado General Norte
    static double Subtotal = 0; //subtotal
    
    public static String desplegarFecha () {
        Date date = new Date();
        DateFormat hourdateFormat = new SimpleDateFormat("HH:mm:ss dd/MM/yyyy");
        return hourdateFormat.format(date);
}

    public static void parteAdministrador() {

        camposVIP_A = (int) Integer.parseInt(JOptionPane.showInputDialog
        ("digite la cantidad de campos disponibles en la Seccion VIP A "));
        precioVIP_A = (double) Integer.parseInt(JOptionPane.
                showInputDialog("digite el precio de los campos en la Seccion "
                        + "VIP A "));

        camposVIP_B = (int) Integer.parseInt(JOptionPane.showInputDialog
        ("digite la cantidad de campos disponibles en la Seccion VIP B "));
        precioVIP_B = (double) Integer.parseInt(JOptionPane.
                showInputDialog("digite el precio de los campos en la Seccion "
                        + "VIP B "));

        camposPlateaPreferencia_A = (int) Integer.parseInt(JOptionPane.
               showInputDialog("digite la cantidad de campos disponibles en la "
                        + "SeccionPlatea Preferencial A "));
        precioPlateaPreferencia_A = (double) Integer.parseInt(
             JOptionPane.showInputDialog("digite el precio de los campos en la "
                        + "Seccion Platea Preferencial A "));

        camposPlateaPreferencia_B = (int) Integer.parseInt(JOptionPane.
                showInputDialog("digite la cantidad de campos disponibles "
                + "en la Seccion Platea Preferencial B "));
        precioPlateaPreferencia_B = (double) Integer.parseInt
        (JOptionPane.showInputDialog("digite el precio de los campos en la "
                + "Seccion Platea Preferencial B "));

        camposGeneralEste = (int) Integer.parseInt(JOptionPane.
                showInputDialog("digite la cantidad de campos disponibles en la "
                        + "Seccion General Este "));
        precioGeneralEste = (double) Integer.parseInt(JOptionPane.
                showInputDialog("digite el precio de los  campos disponibles en "
                        + "la Seccion General Este "));

        camposGeneralOeste = (int) Integer.parseInt(JOptionPane.
                showInputDialog("digite la cantidad de campos disponibles en "
                        + "la Seccion General Oeste "));
        precioGeneralOeste = (double) Integer.parseInt(JOptionPane.
                showInputDialog("digite el precio de los  campos disponibles "
                        + "en la Seccion General Oeste "));

        camposGeneralNorte = (int) Integer.parseInt(JOptionPane.
                showInputDialog("digite la cantidad de campos disponibles en "
                        + "la Seccion General Norte "));
        precioGeneralNorte = (double) Integer.parseInt(JOptionPane.
                showInputDialog("digite el precio de los  campos disponibles "
                        + "en la Seccion General Norte "));
    }
    
    public static void ventaEntradas(){
        

        String nombre = JOptionPane.showInputDialog("Digite el nombre "
                + "del cliente");
        int camposComprados = 0;

        try{
            camposComprados = (int) Integer.parseInt(JOptionPane.showInputDialog
        ("Digite la cantidad de campos que desea comprar "));
        }catch(Exception e) {
            camposComprados = (int) Integer.parseInt(JOptionPane.showInputDialog
        ("Valor no Válido, por favor ingrese la cantidad de campos que desea comprar "));
        }

        while (counter <= camposComprados) {

            int Seccion = (int) Integer.parseInt(JOptionPane.showInputDialog
        ("Digite la seccion: \n VIP"
                    + " A(1), \n VIP B(2),\n PlateaPreferencial A(3), "
                    + "\nPlateaPreferencial B(4), \nGeneral Este(5), "
                    + "\n General Oeste (6) \n o General Norte (7)"));

            switch (Seccion) {
                case 1:
                    int camposVIPA = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                                    + "desea comprar en la seccion VIP A "));
                    camposVIP_A  = camposVIP_A -camposVIPA;
                    if(camposVIP_A >= 0 ){
                    VIPA= VIPA + camposVIPA;
                    TotalPagarCampos = camposVIPA * precioVIP_A;
                    ImpuestoVIPA = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarVIPA = TotalAPagarVIPA + (TotalPagarCampos + ImpuestoVIPA);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                            + "entradas compradas: \n VIP A:" + VIPA + "\n total "
                            + "pagado por seccion VIP A: ₡" + TotalAPagarVIPA);
                    }else{
                    JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                    break;
                case 2:
                    int camposVIPB = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                                    + "desea comprar en la seccion VIP B "));
                    camposVIP_B = camposVIP_B -camposVIPB;
                     if(camposVIP_B >= 0 ){
                    VIPB= VIPB + camposVIPB;
                    TotalPagarCampos = camposVIPB * precioVIP_B;
                    ImpuestoVIPB = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarVIPB = TotalAPagarVIPB + (TotalPagarCampos + ImpuestoVIPB);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                     + "entradas compradas:\n VIP B:" + VIPB + "\n total pagado "
                            + "por seccion VIP B: ₡" + TotalAPagarVIPB);}
                     else{
                     JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                     
                    break;
                case 3:
                    int camposPA = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                               + "desea comprar en la seccion PREFERECIAL A "));
                    camposPlateaPreferencia_A =camposPlateaPreferencia_A -camposPA;
                    if(camposPlateaPreferencia_A >= 0 ){
                    PreferencialA=PreferencialA +camposPA;
                    TotalPagarCampos = camposPA * precioPlateaPreferencia_A;
                    ImpuestoPreferencialA = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarPreferencialA = TotalAPagarPreferencialA + (TotalPagarCampos + ImpuestoPreferencialA);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                      + "entradas compradas:\n Platea A:" + PreferencialA + "total pagado"
                            + " por seccion Platea A: ₡" + TotalAPagarPreferencialA);}
                    else{
                         JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                    
                    break;
                case 4:
                    int camposPB = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                               + "desea comprar en la seccion PREFERECIAL B "));
                    camposPlateaPreferencia_B=camposPlateaPreferencia_B-camposPB;
                    if(camposPlateaPreferencia_B >= 0 ){
                    PreferencialB= PreferencialB +camposPB;
                    TotalPagarCampos = camposPB * precioPlateaPreferencia_B;
                    ImpuestoPreferencialB = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarPreferencialB = TotalAPagarPreferencialB + (TotalPagarCampos + ImpuestoPreferencialB);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                      + "entradas compradas:\n Platea B:" + PreferencialB + "total pagado"
                            + " por seccion Platea B: ₡" + TotalAPagarPreferencialB);}
                    else{
                        JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                    
                    break;
                case 5:
                    int camposGE = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                                + "desea comprar en la seccion GENERAL ESTE "));
                    camposGeneralEste=camposGeneralEste-camposGE;
                     if(camposGeneralEste >= 0 ){
                    GeneralEste= GeneralEste + camposGE;
                    TotalPagarCampos = camposGE * precioGeneralEste;
                    ImpuestoGeneralEste = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarGeneralEste = TotalAPagarGeneralEste + (TotalPagarCampos + ImpuestoGeneralEste);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                        + "entradas compradas:\n General Este:" + GeneralEste + "total "
                            + "pagado por seccion General Este: ₡" + TotalAPagarGeneralEste);}
                         else{
                        JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                     
                    break;
                case 6:
                    int camposGO = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                              + "desea comprar en la seccion GENERAL OESTE "));
                    camposGeneralOeste=camposGeneralOeste - camposGO;
                    if(camposGeneralOeste >= 0 ){
                    GeneralOeste= GeneralOeste + camposGO;
                    TotalPagarCampos = camposGO * precioGeneralOeste;
                    ImpuestoGeneralOeste = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarGeneralOeste = TotalAPagarGeneralOeste + (TotalPagarCampos + ImpuestoGeneralOeste);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                       + "entradas compradas:\n General Oeste:" + GeneralOeste + "total "
                            + "pagado por seccion General Oeste: ₡" + TotalAPagarGeneralOeste);}
                         else{
                        JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                    break;
                case 7:
                    int camposGN = (int) Integer.parseInt(JOptionPane.
                            showInputDialog("Digite la cantidad de campos que "
                              + "desea comprar en la seccion GENERAL NORTE "));
                    camposGeneralNorte = camposGeneralNorte -camposGN;
                    if(camposGeneralNorte >= 0 ){
                    GeneralNorte= GeneralNorte + camposGN;
                    TotalPagarCampos = camposGN * precioGeneralNorte;
                    ImpuestoGeneralNorte = TotalPagarCampos * 0.13;
                    counter = counter + VIPA+ VIPB+  PreferencialA + PreferencialB +  GeneralEste+ GeneralOeste + GeneralNorte;
                    TotalAPagarGeneralNorte = TotalAPagarGeneralNorte + (TotalPagarCampos + ImpuestoGeneralNorte);
                    JOptionPane.showMessageDialog(null, "Seccion Y Numero de "
                        + "entradas compradas:\n General Norte:" + GeneralNorte + "total "
                            + "pagado por seccion General Oeste: ₡" + TotalAPagarGeneralNorte);}
                         else{
                        JOptionPane.showMessageDialog(null, "NO HAY CAMPOS DISPONIBLES");}
                    break;
                default:
                    JOptionPane.showMessageDialog(null, "VALOR INCORRECTO");
            }
            
            Total_A_Apagar = Total_A_Apagar + TotalAPagarVIPA + TotalAPagarVIPB + TotalAPagarPreferencialA + TotalAPagarPreferencialB + TotalAPagarGeneralOeste + TotalAPagarGeneralEste + TotalAPagarGeneralNorte;
            Subtotal = Subtotal + TotalPagarCampos;
            Impuesto = Impuesto + ImpuestoVIPA + ImpuestoVIPB + ImpuestoPreferencialA + ImpuestoPreferencialB + ImpuestoGeneralEste + ImpuestoGeneralOeste + ImpuestoGeneralNorte;

        }

        // factura proforma
        JOptionPane.showMessageDialog(null, "Fecha  y hora de la compra "+ desplegarFecha()
                + "\n El cliente :" + nombre
                + "\n Subtotal ₡ " + Subtotal + "\n el total de impuestos es de: ₡"
                + Impuesto + "\n EL TOTAL A PAGAR ES DE: ₡" + Total_A_Apagar, "Factura",
                JOptionPane.WARNING_MESSAGE);

    }
    
    
    public static void formaDePago(){
        String[] choices = { "American Express", "Mastercard", "Visa"};
    String input = (String) JOptionPane.showInputDialog(null, "Escoja",
        "Tipo de Tarjeta", JOptionPane.QUESTION_MESSAGE, null, 
        choices, 
        choices[1]); 
    System.out.println(input);
  }

    
            
    public static void main(String[] args) {
        parteAdministrador();
        ventaEntradas();
        formaDePago();
    }
    
}
