import java.awt.*;

public class HomePage extends javax.swing.JPanel {

    public HomePage() {
        initComponents();
    }
    
    private void initComponents() {
        
        setBackground(new Color(0X5CDB95));
        
        welcomeLabel = new javax.swing.JLabel();
        welcomeLabel1 = new javax.swing.JLabel();

        welcomeLabel.setFont(new java.awt.Font("MV Boli", Font.BOLD, 45));
        welcomeLabel.setText("Welcome");

        welcomeLabel1.setFont(new java.awt.Font("MV Boli", Font.BOLD, 45)); 
        welcomeLabel1.setText("To Your Dashboard");

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(this);
        this.setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addGap(170, 170, 170)
                        .addComponent(welcomeLabel))
                    .addGroup(layout.createSequentialGroup()
                        .addGap(71, 71, 71)
                        .addComponent(welcomeLabel1)))
                .addContainerGap(83, Short.MAX_VALUE))
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addGap(96, 96, 96)
                .addComponent(welcomeLabel, javax.swing.GroupLayout.PREFERRED_SIZE, 48, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.UNRELATED)
                .addComponent(welcomeLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 48, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(169, Short.MAX_VALUE))
        );
    }                    
    javax.swing.JLabel welcomeLabel;
    javax.swing.JLabel welcomeLabel1;
}
