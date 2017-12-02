
# Pourquoi la famille des patterns comportementaux ?

L'une des raisons principales est que le pattern State est utilisé pour **changer le comportement** d'un objet sans toucher à son instanciation.


# Passons à un exemple

Imaginons que nous souhaitons coder un lecteur vidéo très simple. Ce lecteur pourra uniquement lire une vidéo ou la mettre ne pause.
Nous voyons donc facilement qu'il n'y que deux états différents possible pour une vidéo dans ce logiciel:
-**Lecture**
-**Pause**

Evidemment, nous pourrions coder ce programme de cette manière :
``` java runnable 
public class Video {

	private String etat="";

	public void setEtat(String etat){
		this.etat=etat;
	}

	public void action(){
		if(etat.equalsIgnoreCase("PLAY")){
			System.out.println("La vidéo est en lecture");
		}else if(etat.equalsIgnoreCase("PAUSE")){
			System.out.println("La vidéo est en pause");
		}
	}

	public static void main(String args[]){
		Video video = new Video();

		video.setEtat("PLAY");
		video.action();

		video.setEtat("PAUSE");
		video.action();
	}
}
```
