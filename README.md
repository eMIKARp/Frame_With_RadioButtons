# Frame_With_RadioButtons
a piece of code that displays a frame with radio buttons which change the font size of a label

    package przelaczniki;

    import javax.swing.*;
    import java.awt.*;
    import java.awt.event.*;


    public class Main extends JFrame            

    {
  
    public Main()                           
    {
        initComponents();                   
    }
    
       
    JPanel panel1 = new JPanel();
    JPanel panel2 = new JPanel();
    JLabel label = new JLabel("Lorem ipusm");
    ButtonGroup groupSize = new ButtonGroup();
  
    public void initComponents() 
    {
        this.setTitle("Grupy przełączników typu Radio");
        this.setBounds(300, 300, 400, 100);
        
        zbudujPrzelacznik("Mały", 10);
        zbudujPrzelacznik("Średni", 20);
        zbudujPrzelacznik("Duży", 30);
        zbudujPrzelacznik("Wielki", 40);
              
        panel2.add(label);
        
        this.getContentPane().add(panel1, BorderLayout.NORTH);
        this.getContentPane().add(panel2, BorderLayout.CENTER);
        this.setDefaultCloseOperation(3);
    }
    
     public void zbudujPrzelacznik(String nazwa, final int rozmiar)
     {
            JRadioButton nowyButton = new JRadioButton(nazwa);
            groupSize.add(nowyButton);  
            panel1.add(nowyButton);
            nowyButton.addActionListener(new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) 
                {
                   label.setFont(new Font("Monospaced", Font.ITALIC, rozmiar));
                }
            });

     }   
    
    
    public static void main(String[] args) 
    {
        new Main().setVisible(true);   
    }
    }
