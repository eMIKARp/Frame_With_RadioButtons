# Frame_With_RadioButtons
a piece of code that displays a frame with radio buttons which change the font size and color of a label

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
    JPanel panel3 = new JPanel();
    JLabel label = new JLabel("Lorem ipusm");
    ButtonGroup groupSize = new ButtonGroup();
    ButtonGroup groupColor = new ButtonGroup();
  
    public void initComponents() 
    {
        this.setTitle("Grupy przełączników typu Radio");
        this.setBounds(300, 300, 400, 100);
        
        zbudujPrzelacznikRozmiaru("Mały", 10);
        zbudujPrzelacznikRozmiaru("Średni", 20);
        zbudujPrzelacznikRozmiaru("Duży", 30);
        zbudujPrzelacznikRozmiaru("Wielki", 40);
        
        zbudujPrzelacznikKoloru("Czerwony", Color.RED);
        zbudujPrzelacznikKoloru("Niebieski", Color.BLUE);
        zbudujPrzelacznikKoloru("Żółty", Color.YELLOW);
        
              
        panel3.add(label);
        
        this.getContentPane().add(panel1, BorderLayout.NORTH);
        this.getContentPane().add(panel2, BorderLayout.CENTER);
        this.getContentPane().add(panel3, BorderLayout.SOUTH);
        
        this.setDefaultCloseOperation(3);
    }
    
     public void zbudujPrzelacznikRozmiaru(String nazwa, final int rozmiar)
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
     
     public void zbudujPrzelacznikKoloru(String nazwa, final Color kolor)
     {
            JRadioButton nowyButton = new JRadioButton(nazwa);
            groupColor.add(nowyButton);  
            panel2.add(nowyButton);
            nowyButton.addActionListener(new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) 
                {
                   label.setForeground(kolor);
                }
            });    

     }   
    
    
    public static void main(String[] args) 
    {
        new Main().setVisible(true);   
    }
    }

