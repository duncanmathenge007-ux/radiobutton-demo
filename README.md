import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class RadioButtonDemo extends JFrame implements ActionListener {
    private JRadioButton birdButton, catButton, dogButton, rabbitButton, pigButton;
    private JLabel imageLabel;
    private ButtonGroup group;

    public RadioButtonDemo() {
        setTitle("RadioButtonDemo");
        setSize(500, 400);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());
        birdButton = new JRadioButton("Bird");
        catButton = new JRadioButton("Cat");
        dogButton = new JRadioButton("Dog");
        rabbitButton = new JRadioButton("Rabbit");
        pigButton = new JRadioButton("Pig");
        
        group = new ButtonGroup();
        group.add(birdButton);
        group.add(catButton);
        group.add(dogButton);
        group.add(rabbitButton);
        group.add(pigButton);

        birdButton.addActionListener(this);
        catButton.addActionListener(this);
        dogButton.addActionListener(this);
        rabbitButton.addActionListener(this);
        pigButton.addActionListener(this);

        
        add(birdButton);
        add(catButton);
        add(dogButton);
        add(rabbitButton);
        add(pigButton);

    
        imageLabel = new JLabel();
        add(imageLabel);

        setVisible(true);
    }
    public void actionPerformed(ActionEvent e) {
        String choice = e.getActionCommand();
        JOptionPane.showMessageDialog(this, "You selected: " + choice);

        switch (choice) {
            case "Bird":
                imageLabel.setIcon(new ImageIcon("images/bird.png"));
                break;
            case "Cat":
                imageLabel.setIcon(new ImageIcon("images/cat.png"));
                break;
            case "Dog":
                imageLabel.setIcon(new ImageIcon("images/dog.png"));
                break;
            case "Rabbit":
                imageLabel.setIcon(new ImageIcon("images/rabbit.png"));
                break;
            case "Pig":
                imageLabel.setIcon(new ImageIcon("images/pig.png"));
                break;
        }
    }

    public static void main(String[] args) {
        new RadioButtonDemo();
    }
}
