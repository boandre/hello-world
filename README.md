import javax.swing.*;
import java.awt.GridLayout;
import java.awt.event.ActionListener;
import java.awt.event.ActionEvent;

public class ExempleSansFils extends JFrame
                            implements ActionListener {
  // Constructeur
  ExempleSansFils() {
    // Crée un cadre contenant un bouton et un champ textuel
    GridLayout disposition = new GridLayout(2,1); 
    this.getContentPane().setLayout(disposition);
    JButton monBouton = new JButton("Tuer le temps");
    monBouton.addActionListener(this);
    this.getContentPane().add(monBouton);    
    this.getContentPane().add(new JTextField());
  }
  // Traite les clics sur le bouton
  public void actionPerformed(ActionEvent événement) {
    // Tue juste un peu le temps pour montrer que
    // les contrôles de la fenêtre sont verrouillés.
    for (int i = 0; i < 30000; i++) {
      this.setTitle("i = " + i);
    }
  }
	
  public static void main(String[] args) {
    // Crée une instance du cadre
    ExempleSansFils maFenêtre = new ExempleSansFils();
    // Permet la fermeture de la fenêtre par clic sur la 
    // petite croix dans le coin.
    maFenêtre.setDefaultCloseOperation(
                      WindowConstants.EXIT_ON_CLOSE);
		
    // Affecte sa taille au cadre - coordonnées du coin haut 
    // gauche, largeur et hauteur.
    maFenêtre.setBounds(0, 0, 200, 100);
    // Rend la fenêtre visible.
    maFenêtre.setVisible(true);
  }
}
