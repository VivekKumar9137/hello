 private void jButton2ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        String aadharno = tf11.getText();
        String Nam=tf12.getText();
        String state=tf13.getText();
        String father=tf14.getText();
        String dcity=tf15.getText();
        String address=tf16.getText();
        String gender=jc2.getSelectedItem().toString();
        String mobile=tf18.getText();
        String dob=tf20.getText();
        String Email=t1.getText();
        String vid=t2.getText();
        String Nat=jl3.getText();
       
        try {
            Class.forName("java.sql.DriverManager");
            Connection con=(Connection)
                    DriverManager.getConnection("jdbc:mysql://localhost:3306/project","root","vivek");
            Statement stmt=(Statement) con.createStatement();
            String query="insert into project12 values('"+aadharno+"','"+Nam+"','"+father+"','"+state+"'," +
            "'"+dcity+"','"+address+"','"+gender+"','"+mobile+"','"+dob+"','"+Email+"','"+Nat+"','"+vid+"');";
            stmt.executeUpdate(query);
             JOptionPane.showMessageDialog(this,"Your Aadhar has created");
        tf11.setText("");
        tf12.setText("");
        tf13.setText("");
        tf14.setText("");
        tf15.setText("");
        tf16.setText("");
        jc2.setSelectedItem(false);
        tf18.setText("");
        tf20.setText("");
        t1.setText("");
        t2.setText("");
        jl3.setText("");
            }
        
       catch(Exception u) {
            JOptionPane.showMessageDialog(this,u.getMessage());
        }
}                                        
