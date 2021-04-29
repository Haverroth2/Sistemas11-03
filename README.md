//pacote
package sample.model;

//classe pública Contato
public class Contato {
   //atributos
   private String whatsapp;
   private String email;
   private String twitter;

   //get and set
   public String getWhatsapp() {
       return whatsapp;
   }

   public void setWhatsapp(String whatsapp) {
       this.whatsapp = whatsapp;
   }

   public String getEmail() {
       return email;
   }

   public void setEmail(String email) {
       this.email = email;
   }

   public String getTwitter() {
       return twitter;
   }

   public void setTwitter(String twitter) {
       this.twitter = twitter;
   }

//sobreescrita ToString
   @Override
   public String toString() {
       return "Contato{" +
               "whatsapp='" + whatsapp + '\'' +
               ", email='" + email + '\'' +
               ", twitter='" + twitter + '\'' +
               '}';
   }
}



//pacote
package sample.model;

//classe Pessoa
public class Pessoa {
   //atributos
   private String nome;
   private Contato contato;

   public Pessoa(String nome){
       this.nome = nome;
       contato = new Contato();
   }
   //get and set


   public String getNome() {
       return nome;
   }

   public void setNome(String nome) {
       this.nome = nome;
   }

   public Contato getContato() {return contato; }
   public void setContato(String whatsapp, String email, String twitter){
       contato.setWhatsapp(whatsapp);
       contato.setTwitter(twitter);
       contato.setEmail(email);
   }

//sobreescrita ToString
   @Override
   public String toString() {
       return "Pessoa{" +
               "nome='" + nome + '\'' +
               ", contato=" + contato +
               '}';
   }
}








//pacote Main
package sample;

//pacote importado Pessoa
import sample.model.Pessoa;

//classe Main
public class Main {

//atributos
   public static void main(String[] args) {
       Pessoa pessoa = new Pessoa("Pedro");
       pessoa.setContato("89-999-11111", "email@email.com", "Ti4p3");
       System.out.println(pessoa);
   }
}


































//pacote
package sample.model;

//pacotes importados
import java.util.ArrayList;
import java.util.List;

//classe pública ItensDoPedido
public class ItensDoPedido {
//listas privadas
   private List<Produto> produtos;

   public List<Produto> getProdutos() {
       return produtos;
   }

   public void setProduto(Produto produto) {
       if (this.produtos == null) {
           this.produtos = new ArrayList<>();
       }

       produtos.add(produto);
   }

   public void setProduto(String nomeProduto, double preco) {

       if(this.produtos == null){
           this.produtos = new ArrayList<>();
       }

       Produto produto = new Produto();
       produto.setNome(nomeProduto);
       produto.setPreco(preco);

       this.produtos.add(produto);


//sobreescrita ToString
       @Override
       public String toString() {
           return "ItensDoPedido{" +
                   "produtos=" + produto;
       }

   }
}





//pscote
package sample.model;

//classe Pedido
public class Pedido {
//atributos
   private String desc;
   private Stringm data;
   private double total;
   private ItensDoPedido itens;

//métodos
   public Pedido(){ itens = new ItensDoPedido(); }

   public String getDesc() { return desc; }

   public void setDesc(String desc) { this.desc = desc; }

   public Stringm getData() { return data; }

   public void setData(Stringm data) { this.data = data; }

   public double getTotal() { return total; }

   public void addProduto(String nomeProduto, double preco){
       itens.setProduto(nomeProduto, preco);
       total += preco;
   }

//ToString
   public String toString(){
       return "Pedido\n"
               + "Descrição: " + desc
               + "Data: " + data + "\n"
               + itens
               + "\nTotal: " + total;
   }
}



//pacote 
package sample.model;

//classe Produto
public class Produto {
//atributos
   private String nome;
   private double preco;

//métodos
   public String getNome() { return nome; }
   public void setNome(String nome) { this.nome = nome; }
   public double getPreco() { return preco; }
   public void setPreco(double preco) { this.preco = preco; }

//sobreescrita ToString
   @Override
   public String toString() {
       return "Produto: " +
                nome +
               ", Preço R$" + preco;
   }
}




























//main
package sample;

//pacotes importados
import sample.model.ItensDoPedido;
import sample.model.Produto;

//classe Main
public class Main {


   public static void main(String[] args) {
//        ItensDoPedido itensDoPedido = new ItensDoPedido();
//
//        Produto produto = new Produto();
//        produto.setNome("Laranja");
//        produto.setPreco(2.4);
//        ItensDoPedido.setProduto(produto);
//
//        ItensDoPedido.setProduto("Uva", 4.7);
//        System.out.println(itensDoPedido);


//informações dos atributos
       Pedido pedido = new Pedido();
       pedido.setDesc("Pedido do Ifood");
       pedido.setData("11/03/21");
       pedido.addProduto("Uva", 5.4);
       pedido.addProduto("Maça", 3.2);
       pedido.addProduto("Banana", 4.4);

       System.out.println(pedido);
   }
}
