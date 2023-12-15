import java.awt.Color;
import java.sql.ResultSet;
import java.sql.SQLException;
import javax.swing.JOptionPane;

public class PurchasePage extends javax.swing.JPanel {

    ProductDTO productDTO;
    
    public PurchasePage(Dashboard dashboard) {
        initComponents();
        loadDataSet();
    }

        private void initComponents() {

        jLabel1 = new javax.swing.JLabel();
        jSeparator1 = new javax.swing.JSeparator();
        jPanel1 = new javax.swing.JPanel();
        jLabel3 = new javax.swing.JLabel();
        jLabel4 = new javax.swing.JLabel();
        jLabel6 = new javax.swing.JLabel();
        jLabel7 = new javax.swing.JLabel();
        jLabel8 = new javax.swing.JLabel();
        codeText = new javax.swing.JTextField();
        nameText = new javax.swing.JTextField();
        quantityText = new javax.swing.JTextField();
        costText = new javax.swing.JTextField();
        sellText = new javax.swing.JTextField();
        purchaseButton = new javax.swing.JButton();
        jScrollPane1 = new javax.swing.JScrollPane();
        purchaseTable = new javax.swing.JTable();

        setBackground(new Color(0X8EE4AF));
        jSeparator1.setBackground(new Color(0X05386B));

        jLabel1.setFont(new java.awt.Font("MV Boli", 0, 15));
        jLabel1.setText("SALES");

        jPanel1.setBorder(javax.swing.BorderFactory.createTitledBorder("Sales Info"));

        jLabel3.setText("Product Code:");

        jLabel4.setText("Product Name:");

        jLabel6.setText("Quantity:");

        jLabel7.setText("Cost Price:");

        jLabel8.setText("Selling Price:");

        codeText.addKeyListener(new java.awt.event.KeyAdapter() {
            public void keyReleased(java.awt.event.KeyEvent evt) {
                codeTextKeyReleased(evt);
            }
        });

        purchaseButton.setText("Sales");
         purchaseButton.setBackground(new Color(0X05386B));
        purchaseButton.setForeground(new Color(0XEDF5E1));
        purchaseButton.setFocusable(false);
        purchaseButton.addActionListener(new java.awt.event.ActionListener() {
            public void actionPerformed(java.awt.event.ActionEvent evt) {
                purchaseButtonActionPerformed(evt);
            }
        });

        javax.swing.GroupLayout jPanel1Layout = new javax.swing.GroupLayout(jPanel1);
        jPanel1.setLayout(jPanel1Layout);
        jPanel1. setBackground(new Color(0X8EE4AF));
        jPanel1Layout.setHorizontalGroup(
            jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addContainerGap()
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addComponent(jLabel3, javax.swing.GroupLayout.PREFERRED_SIZE, 102, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(codeText, javax.swing.GroupLayout.DEFAULT_SIZE, 173, Short.MAX_VALUE))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addComponent(jLabel4, javax.swing.GroupLayout.PREFERRED_SIZE, 102, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(nameText))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addComponent(jLabel6, javax.swing.GroupLayout.PREFERRED_SIZE, 102, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(quantityText))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addComponent(jLabel7, javax.swing.GroupLayout.PREFERRED_SIZE, 102, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(costText))
                    .addGroup(jPanel1Layout.createSequentialGroup()
                        .addComponent(jLabel8, javax.swing.GroupLayout.PREFERRED_SIZE, 102, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(sellText)))
                .addContainerGap())
            .addGroup(javax.swing.GroupLayout.Alignment.TRAILING, jPanel1Layout.createSequentialGroup()
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addComponent(purchaseButton, javax.swing.GroupLayout.PREFERRED_SIZE, 113, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(34, 34, 34))
        );
        jPanel1Layout.setVerticalGroup(
            jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(jPanel1Layout.createSequentialGroup()
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE)
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel3, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(codeText, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel4, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(nameText, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel6, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(quantityText, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel7, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(costText, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(jPanel1Layout.createParallelGroup(javax.swing.GroupLayout.Alignment.BASELINE)
                    .addComponent(jLabel8, javax.swing.GroupLayout.PREFERRED_SIZE, 26, javax.swing.GroupLayout.PREFERRED_SIZE)
                    .addComponent(sellText, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE))
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(purchaseButton, javax.swing.GroupLayout.PREFERRED_SIZE, 31, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addGap(29, 29, 29))
        );

        purchaseTable.setModel(new javax.swing.table.DefaultTableModel(
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
        
        purchaseTable.setBackground(new Color(0XEDF5E1));

        purchaseTable.addMouseListener(new java.awt.event.MouseAdapter() {
            public void mouseClicked(java.awt.event.MouseEvent evt) {
                purchaseTableMouseClicked(evt);
            }
        });
        jScrollPane1.setViewportView(purchaseTable);

        javax.swing.GroupLayout layout = new javax.swing.GroupLayout(this);
        this.setLayout(layout);
        layout.setHorizontalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addComponent(jSeparator1)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 112, javax.swing.GroupLayout.PREFERRED_SIZE)
                        .addGap(0, 0, Short.MAX_VALUE))
                    .addGroup(layout.createSequentialGroup()
                        .addComponent(jScrollPane1, javax.swing.GroupLayout.DEFAULT_SIZE, 459, Short.MAX_VALUE)
                        .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                        .addComponent(jPanel1, javax.swing.GroupLayout.PREFERRED_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.PREFERRED_SIZE)))
                .addContainerGap())
        );
        layout.setVerticalGroup(
            layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING)
            .addGroup(layout.createSequentialGroup()
                .addContainerGap()
                .addComponent(jLabel1, javax.swing.GroupLayout.PREFERRED_SIZE, 43, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addComponent(jSeparator1, javax.swing.GroupLayout.PREFERRED_SIZE, 10, javax.swing.GroupLayout.PREFERRED_SIZE)
                .addPreferredGap(javax.swing.LayoutStyle.ComponentPlacement.RELATED)
                .addGroup(layout.createParallelGroup(javax.swing.GroupLayout.Alignment.LEADING, false)
                    .addComponent(jScrollPane1, javax.swing.GroupLayout.PREFERRED_SIZE, 0, Short.MAX_VALUE)
                    .addComponent(jPanel1, javax.swing.GroupLayout.DEFAULT_SIZE, javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
                .addContainerGap(javax.swing.GroupLayout.DEFAULT_SIZE, Short.MAX_VALUE))
        );
    }                     

    private void purchaseTableMouseClicked(java.awt.event.MouseEvent evt) {                                           
        int row = purchaseTable.getSelectedRow();
        int col = purchaseTable.getColumnCount();

        Object[] data = new Object[col];
        for (int i=0; i<col; i++)
            data[i] = purchaseTable.getValueAt(row, i);
        
        Integer.parseInt(data[3].toString());
        data[1].toString();
    }                                          

    private void purchaseButtonActionPerformed(java.awt.event.ActionEvent evt) {                                               
        productDTO = new ProductDTO();
        productDTO.setSuppCode("12");
        productDTO.setProdCode(codeText.getText());
        try {
            ResultSet resultSet = new ProductDAO().getProdName(codeText.getText());
            if (resultSet.next()) {
                productDTO.setDate("02/01/2020");
                productDTO.setQuantity(Integer.parseInt(quantityText.getText()));
                Double costPrice = Double.parseDouble(costText.getText());
                Double totalCost = costPrice * Integer.parseInt(quantityText.getText());
                productDTO.setTotalCost(totalCost);

                new ProductDAO().addPurchaseDAO(productDTO);
                loadDataSet();
            } else
            JOptionPane.showMessageDialog(null, "Please add this product in the \"Products\" section before proceeding.");
        } catch (SQLException e) {
        }
    }                                              

    private void codeTextKeyReleased(java.awt.event.KeyEvent evt) {                                     
        try {
            ResultSet resultSet = new ProductDAO().getProdFromCode(codeText.getText());
            if (resultSet.next()) {
                nameText.setText(resultSet.getString("productname"));
                costText.setText(String.valueOf(resultSet.getDouble("costprice")));
                sellText.setText(String.valueOf(resultSet.getDouble("sellprice")));
            } else {
                nameText.setText("");
                costText.setText("");
                sellText.setText("");
            }
        } catch (SQLException e) {
        }
    }                                    

    public void loadDataSet() {
        try {
            ProductDAO productDAO = new ProductDAO();
            purchaseTable.setModel(productDAO.buildTableModel(productDAO.getPurchaseInfo()));
        } catch (SQLException throwables) {
        }
    }

    public void loadSearchData(String text) {
        try {
            ProductDAO productDAO = new ProductDAO();
            purchaseTable.setModel(productDAO.buildTableModel(productDAO.getPurchaseSearch(text)));
        } catch (SQLException e) {
        }
    }
    
    javax.swing.JTextField codeText;
    javax.swing.JTextField costText;
    javax.swing.JLabel jLabel1;
    javax.swing.JLabel jLabel3;
    javax.swing.JLabel jLabel4;
    javax.swing.JLabel jLabel6;
    javax.swing.JLabel jLabel7;
    javax.swing.JLabel jLabel8;
    javax.swing.JPanel jPanel1;
    javax.swing.JScrollPane jScrollPane1;
    javax.swing.JSeparator jSeparator1;
    javax.swing.JTextField nameText;
    javax.swing.JButton purchaseButton;
    javax.swing.JTable purchaseTable;
    javax.swing.JTextField quantityText;
    javax.swing.JTextField sellText;
}
