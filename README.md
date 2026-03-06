import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class RadioButtonDemo extends JFrame implements ActionListener {
    private JRadioButton birdButton, catButton, dogButton, rabbitButton, pigButton;
    private JLabel petImage;

    public RadioButtonDemo() {
        setTitle("RadioButtonDemo");
        setSize(400, 400);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        setLayout(new FlowLayout());

        // Create radio buttons
        birdButton = new JRadioButton("Bird");
        catButton = new JRadioButton("Cat");
        dogButton = new JRadioButton("Dog");
        rabbitButton = new JRadioButton("Rabbit");
        pigButton = new JRadioButton("Pig");

        // Group them so only one can be selected
        ButtonGroup group = new ButtonGroup();
        group.add(birdButton);
        group.add(catButton);
        group.add(dogButton);
        group.add(rabbitButton);
        group.add(pigButton);

        // Add action listeners
        birdButton.addActionListener(this);
        catButton.addActionListener(this);
        dogButton.addActionListener(this);
        rabbitButton.addActionListener(this);
        pigButton.addActionListener(this);

        // Add radio buttons to frame
        add(birdButton);
        add(catButton);
        add(dogButton);
        add(rabbitButton);
        add(pigButton);

        // Image label
        petImage = new JLabel();
        add(petImage);

        setVisible(true);
    }

    @Override
    public void actionPerformed(ActionEvent e) {
        String pet = e.getActionCommand();
        JOptionPane.showMessageDialog(this, "You selected: " + pet);

        // Load image from images folder
        String imagePath = "images/" + pet.toLowerCase() + ".png";
        petImage.setIcon(new ImageIcon(imagePath));
    }

    public static void main(String[] args) {
        new RadioButtonDemo();
    }
}
