# java_project
import java.applet.*;

import java.awt.*;

import java.awt.event.*;

public class Micro extends Applet implements ActionListener,ItemListener {

    Button b1;
    
    Label l1,l2,l3,l4,l5,l6,l7;
    
    TextField t1,t2,t3,t4,t5,t6;
    
    CheckboxGroup cbg;
    
    Checkbox Male,Female;
    
    String msg;
    
    public void init(){
    
       FlowLayout layout=new FlowLayout(25,50,50);
       
        this.setLayout(layout);
        
        b1=new Button("SUBMIT");
        
        b1.addActionListener(this);
        
        l1=new Label("Name",Label.CENTER);
        
        l2=new Label("Post");
        
        l3=new Label("Phone no");
        
        l4=new Label("Address");
        l5=new Label("Experience(In Yrs)");
        l6=new Label("Age");
        l7=new Label("Gender");
        t1=new TextField(20);
        t2=new TextField(20);
        t3=new TextField(25);
        t4=new TextField(25);
        t5=new TextField(25);
        t6=new TextField(25);
        cbg=new CheckboxGroup();
        Male=new Checkbox("Male",cbg,true);
        Female=new Checkbox("Female",cbg,true);
        add(l1);
        add(t1);
        add(l2);
        add(t2);
        add(l3);
        add(t3);
        add(l4);
        add(t4);
        add(l5);
        add(t5);
        add(l6);
        add(t6);
        add(l7);
        add(Male);
        add(Female);
        add(b1);
    }
    public void actionPerformed(ActionEvent ae){
         l1.getAlignment();
        String str1=t1.getText();
        l2.getAlignment();
     
        String str2=t2.getText();
    
        String str3=t3.getText();
        String str4=t4.getText();
        String str5=t5.getText();
        String str6=t6.getText();
        if(ae.getActionCommand().equals("SUBMIT"))
        { 
            if(str1.length()==0||str2.length()==0||str3.length()==0||str4.length()==0||str5.length()==0||str6.length()==0)
                msg="PLEASE FILL ALL THE FIELDS ";
            if(str3.length()==10)
            
            msg="SUBMITTED";
         
             if(str3.length()>10)
            t3.setText("ENTER VALID PHONE NUMBER");
             
            if(str3.length()<10)
            t3.setText("ENTER VALID PHONE NUMBER"); 
            repaint();
            
            
        }
    }
    public void itemStateChanged(ItemEvent ie){
        repaint();
    }
    public void paint(Graphics g)
    {  g.setColor(Color.BLUE);
        g.drawString("JOB APPLICATION",650,15);
        g.setColor(Color.BLUE);
        g.drawString(msg,630,250);
        b1.setBackground(Color.CYAN);
        setBackground(Color.pink);
    }
}
