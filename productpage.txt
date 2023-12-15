import java.awt.Color;
import javax.swing.*;
import java.sql.SQLException;

public class ProductPage extends javax.swing.JPanel {

 
    ProductDTO productDTO;
    String username = null;
    String supplier = null;
    int userID;
    Dashboard dashboard;
    
    
    public ProductPage() {
    }
    
    public ProductPage(String username, Dashboard dashboard){
        initComponents();
        this.username = username;
        this.dashboard = dashboard;
        loadDataSet();
    }

    private void initComponents() {
        jLabel1 = new javax.swing.JLabel();
        jSeparator1 = new javax.swing.JSeparator();
        entryPanel = new javax.swing.JPanel();
        jLabel2 = new javax.swing.JLabel();
        jLabel3 = new javax.swing.JLabel();
        jLabel5 = new javax.swing.JLabel();
        jLabel6 = new javax.swing.JLabel();
        jLabel7 = new javax.swing.JLabel();
        jLabel8 = new javax.swing.JLabel();
        codeText = new javax.swing.JTextField();
        nameText = new javax.swing.JTextField();
        quantityText = new javax.swing.JTextField();
        costText = new javax.swing.JTextField();
        sellText = new javax.swing.JTextField();
        brandText = new javax.swing.JTextField();
        addButton = new javax.swing.JButton();
        jScrollPane1 = new javax.swing.JScrollPane();
        productTable = new javax.swing.JTable();

        setBackground(new Color(0X8EE4AF));
        jLabel1.setFont(new java.awt.Font("MV Boli", 0, 15)); 
        jLabel1.setText("PRODUCTS");

        entryPanel.setBorder(javax.swing.BorderFactory.createTitledBorder("Enter Product Details"));

        jLabel2.setText("Product Code:");

        jLabel3.setText("Product Name:");

        jLabel5.setText("Quantity:");

        jLabel6.setText("Cost Price:");

        jLabel7.setText("Selling Price:");

        jLabel8.setText("Brand:");

        addButton.setText("Add");
        addButton.setCursor(new java.awt.Cursor(java.awt.Cursor.HAND_CURSOR));
         addButton.setBackground(new Color(0X05386B));
        addButton.setForeground(new Color(0XEDF5E1));
        addButton.setFocusable(false);
        addButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                addButtonActionPerformed(evt);
            }
        });

        javax.swing.GroupLayout entryPanelLayout = new javax.swing.GroupLayout(entryPanel);
        entryPanel.setLayout(entryPanelLayout);
        entryPanel.setBackground(new Color(0X8EE4AF));
        entryPanelLayout.setHorizontalGroup(
            entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(entryPanelLayout.createSequentialGroup()
                .addContainerGap()
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(entryPanelLayout.createSequentialGroup()
                        .addComponent(jLabel2, javax.swing.GroupLayout.PREFERRED_SIZE, 84, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(codeText))
                    .addGroup(entryPanelLayout.createSequentialGroup()
                        .addComponent(jLabel3, javax.swing.GroupLayout.PREFERRED_SIZE, 84, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(nameText))
                    .addGroup(entryPanelLayout.createSequentialGroup()
                        .addComponent(jLabel5, javax.swing.GroupLayout.PREFERRED_SIZE, 84, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(quantityText))
                    .addGroup(entryPanelLayout.createSequentialGroup()
                        .addComponent(jLabel6, javax.swing.GroupLayout.PREFERRED_SIZE, 84, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(costText))
                    .addGroup(entryPanelLayout.createSequentialGroup()
                        .addComponent(jLabel7, javax.swing.GroupLayout.PREFERRED_SIZE, 84, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(sellText))
                    .addGroup(entryPanelLayout.createSequentialGroup()
                        .addComponent(jLabel8, javax.swing.GroupLayout.PREFERRED_SIZE, 84, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                            .addComponent(brandText)
                            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, entryPanelLayout.createSequentialGroup()
                                .addGap(0, 15, Short.MAX_VALUE)
                                .addComponent(addButton, javax.swing.GroupLayout.PREFERRED_SIZE, 104, javax.swing.GroupLayout.PREFERRED_SIZE)
                                .addGap(28, 28, 28)))))
                .addContainerGap())
        );
        entryPanelLayout.setVerticalGroup(
            entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(entryPanelLayout.createSequentialGroup()
                .addContainerGap()
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel2, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(codeText, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel3, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(nameText, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel5, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(quantityText, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel6, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(costText, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel7, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(sellText, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(entryPanelLayout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel8, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(brandText, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(addButton, javax.swing.GroupLayout.PREFERRED_SIZE, 39, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addContainerGap(140, Short.MAX_VALUE))
        );

        productTable.setModel(new javax.swing.table.DefaultTableModel(
            new Object [][] {
                {null, null, null, null},
                {null, null, null, null},
                {null, null, null, null},
                {null, null, null, null}
            },
            new String [] {
                "Title 1", "Title 2", "Title 3", "Title 4"
            }
        ));
        productTable.setBackground(new Color(0XEDF5E1));
        productTable.setCursor(new java.awt.Cursor(java.awt.Cursor.HAND_CURSOR));
        productTable.addMouseListener(new java.awt.event.MouseAdapter() {
            public void mouseClicked(java.awt.event.MouseEvent evt) {
                productTableMouseClicked(evt);
            }
        });
        jScrollPane1.setViewportView(productTable);

        jSeparator1.setBackground(new Color(0X05386B));
        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(this);
        this.setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 126, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, 596, Short.MAX_VALUE))
                    .addComponent(jSeparator1)
                    .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, layout.createSequentialGroup()
                        .addComponent(jScrollPane1)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(entryPanel, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addContainerGap())
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 41, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addComponent(jSeparator1, javax.swing.GroupLayout.PREFERRED_SIZE, 10, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                    .addComponent(entryPanel, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                    .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, 0, Short.MAX_VALUE))
                .addContainerGap())
        );
    }                       

    private void addButtonActionPerformed(java.awt.event.ActionEvent evt) {                                          
        productDTO = new ProductDTO();
        if (nameText.getText().equals("") || costText.getText().equals("")
                || sellText.getText().equals("") || brandText.getText().equals(""))
            JOptionPane.showMessageDialog(null, "Please enter all the required details.");
        else {
            productDTO.setProdCode(codeText.getText());
            productDTO.setProdName(nameText.getText());
            productDTO.setDate("02/01/2020");
            productDTO.setQuantity(Integer.parseInt(quantityText.getText()));
            productDTO.setCostPrice(Double.parseDouble(costText.getText()));
            productDTO.setSellPrice(Double.parseDouble(sellText.getText()));
            productDTO.setBrand(brandText.getText());
            productDTO.setUserID(userID);

            new ProductDAO().addProductDAO(productDTO);
            loadDataSet();
        }
    }                                         

    //static String productName;
    private void productTableMouseClicked(java.awt.event.MouseEvent evt) {                                          
        int row = productTable.getSelectedRow();
        int col = productTable.getColumnCount();

        Object[] data = new Object[col];
        for (int i=0; i<col; i++)
            data[i] = productTable.getValueAt(row, i);

         codeText.setText(data[0].toString());
        nameText.setText(data[1].toString());
        costText.setText(data[2].toString());
        sellText.setText(data[3].toString());
        brandText.setText(data[4].toString());
    }                                         

    public void loadDataSet() {
        try {
            ProductDAO productDAO = new ProductDAO();
            productTable.setModel(productDAO.buildTableModel(productDAO.getQueryResult()));
        } catch (SQLException throwables) {
            throwables.printStackTrace();
        }
    }

    // Method to display search result in table
    public void loadSearchData(String text) {
        try {
            ProductDAO productDAO = new ProductDAO();
            productTable.setModel(productDAO.buildTableModel(productDAO.getProductSearch(text)));
        } catch (SQLException throwables) {
            throwables.printStackTrace();
        }
    }

     javax.swing.JButton addButton;
     javax.swing.JTextField brandText;
     javax.swing.JTextField codeText;
     javax.swing.JTextField costText;
     javax.swing.JPanel entryPanel;
     javax.swing.JLabel jLabel1;
     javax.swing.JLabel jLabel2;
     javax.swing.JLabel jLabel3;
     javax.swing.JLabel jLabel5;
     javax.swing.JLabel jLabel6;
     javax.swing.JLabel jLabel7;
     javax.swing.JLabel jLabel8;
     javax.swing.JScrollPane jScrollPane1;
     javax.swing.JSeparator jSeparator1;
     javax.swing.JTextField nameText;
     javax.swing.JTable productTable;
     javax.swing.JTextField quantityText;
     javax.swing.JTextField sellText;
}
