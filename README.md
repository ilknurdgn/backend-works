# ⦁	JVM nedir ne işe yarar?
Java 'bir kez yaz,her yerde çalıştır' felsefesiyle platform bağımsızlığını ifade eder.
Platform bağımsızlığını(Java Virtual Macchine) Java Sanal Makinası sağlar.
JVM, tüm platformlarda (GNU-Linux, Windows, MacOs) Java kodlarını çalıştırmak üzere geliştirilmiştir.
Java dilinde program geliştirebilmek için gerekli olan kütüphanelerin bulunduğu geliştirici paketidir.İçerisinde JVM, JRE, Java kütüphaneleri, Java Compiler ve Interpreter içerir.Bu sayede java uygulaması geliştirmek için JDK yüklenmesi yeterlidir.<br/>
<br/>
![JDK](https://miro.medium.com/max/1368/1*RwgVYFTGMpkfVOfBczJGiA.png)
# ⦁	Garbage Collector görevi nedir? Nasıl çalışır?
Java dilinde bir sınıftan oluşturulan nesnenin işi bittiğinde bellekte ona ayrılan yer boşaltılır. Belleği boşaltma işlevi Garbage Collector’dır.Garbace Collector çalışıtığında heapde çalıştıralamayan nesneleri siler.
# ⦁	.jar formatı nedir?
JAR, Java ARŞİVİ anlamına gelir. Adından da anlaşılacağı gibi, bir arşiv dosyası bu, taşınabilirlik ve depolama alanını azaltmak gibi nedenlerle bir arada paketlenmiş, diğer dosyaları içeren tek bir dosya olduğu anlamına gelir.
# ⦁	Javada .class .ve .java formatının farkı nedir?
.java uzantılı dosyalar java programlama dilinde yazılmıştır. .java uzantılı dosyalar derlenerek byte koda dönüştürülür.Bu byte kodlar .class uzantılı dosyalara yazılır.
.calss uzantılı dosyalar programdan bağımsız çalışabilirken .java çalışamaz.
# ⦁	Abstract class nedir,nasıl çalışır,ne işe yarar, 1 tane abstract class örneği
Ortak özellikleri olan nesneleri modellemek için Java dilinde abstract(soyut) sınıflar kullanır.Soyut sınıflar kalıtım özelliğini kullanarak kod tekrarını azaltır.
```
package pkgabstract;
 class Calistir{
 public void Yazdir(Database database){
    database.add();
    database.delete();
    database.get();
    database.update();
}
 }

public class Abstract {

    public static void main(String[] args) {
       /*MysqlDatabase mysqlDatabase=new MysqlDatabase();
        mysqlDatabase.add();
        mysqlDatabase.delete();
        mysqlDatabase.get();
        mysqlDatabase.update();*/
       
       Calistir calistir=new Calistir();
       calistir.Yazdir(new MysqlDatabase());
        System.out.println("**********");
       calistir.Yazdir(new MongoDatabase());
    }
    
}
//Abstract class
package pkgabstract;

public abstract class Database {
    
    public void add(){
        System.out.println("eklendi....");
        
    }
    public void delete(){
        System.out.println("silindi...");
    }
    
    abstract void get();
    abstract void update();
}



public class MongoDatabase extends Database{
     @Override
    public void update(){
        System.out.println("mongo guncellendi...");
            
    }
    @Override
    public void get(){
        System.out.println("mongo bilgiler alindi");
    }
}

public class MysqlDatabase extends Database{
    @Override
    public void update(){
        System.out.println("sql guncellendi...");
            
    }
    @Override
    public void get(){
        System.out.println("sql bilgiler alindi");
    }
}

```
