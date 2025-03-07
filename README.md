# java-assingment-2
write an application that uses five radio buttons to let you choose which kind of pets is displayed
import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class RadioButton {
    public static void main(String[] args) {
        JFrame frame = new JFrame("RadioButton");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setSize(400, 300);
        
        JPanel panel = new JPanel();
        panel.setLayout(new BorderLayout());
        
        JLabel imageLabel = new JLabel();
        imageLabel.setHorizontalAlignment(JLabel.CENTER);
        panel.add(imageLabel, BorderLayout.CENTER);
        
        JPanel radioPanel = new JPanel();
        ButtonGroup group = new ButtonGroup();
        
        String[] pets = {"Bird", "Cat", "Dog", "Rabbit", "Pig"};
        for (String pet : pets) {
            JRadioButton radioButton = new JRadioButton(pet);
            group.add(radioButton);
            radioPanel.add(radioButton);
            
            radioButton.addActionListener(new ActionListener() {
                @Override
                public void actionPerformed(ActionEvent e) {
                    JOptionPane.showMessageDialog(frame, "You selected: " + pet);
                    imageLabel.setIcon(new ImageIcon(pet.toLowerCase() + ".jpeg"));
                }
            });
        }
        
        panel.add(radioPanel, BorderLayout.SOUTH);
        
        frame.add(panel);
        frame.setVisible(true);
    }
}
