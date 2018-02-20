/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package javaapplication11;

import javax.swing.JFrame;
import javax.swing.JOptionPane;



/**
 *
 * @author Hitler
 */
public class JDialogs {
    
    private String string = "";
    private int integer = 0;
    private double db = 0.0;
    
    public String getString(String enteredstring) {
        try{
        string = JOptionPane.showInputDialog(enteredstring);
        
        }catch(Exception e){
            invalid();
        }
      
        return string;
    }
    
    public int getInt(String enteredinteger){
        try{
        integer = Integer.parseInt(JOptionPane.showInputDialog(enteredinteger));
        }catch(Exception e){
            invalid();
        }
        return integer;
    }

    public double getDouble(double entereddouble){
        try{
        db = Double.parseDouble(JOptionPane.showInputDialog(entereddouble));
        }catch(Exception e){
            invalid();
        }
        return db;
    }
   
    public void getMessage(String enteredmessage){
         JOptionPane.showMessageDialog(null,enteredmessage);
    }
    public int getConfirm(String enteredconfirm, String enteredconfirm2){
       int ans =  JOptionPane.showConfirmDialog(null,enteredconfirm,enteredconfirm2,JOptionPane.YES_NO_OPTION);
       int ansyes = 0;
       int ansno = 1;
        if (ans == 0){
            return ansyes;
        }else{return ansno;}
    }
    public static String gender() {
        JFrame frame = new JFrame();
        String[] options = new String[2];
        options[0] = new String("Male");
        options[1] = new String("Female");
        String male = "Male", female = "Female";
        int gender = JOptionPane.showOptionDialog(frame.getContentPane(), "Gender", "Input", 0, JOptionPane.INFORMATION_MESSAGE, null, options, null);
        if (gender == 0) {
            return male;
        } else {
            return female;
        }
    }
    

    public static void invalid() {
        JOptionPane.showMessageDialog(null, "Invalid Entry, Please try again.");
    }
    
}






