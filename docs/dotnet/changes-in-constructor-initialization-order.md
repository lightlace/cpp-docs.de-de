---
title: "&#196;nderungen in der Initialisierungsreihenfolge f&#252;r Konstruktoren"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstruktoren, C++"
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# &#196;nderungen in der Initialisierungsreihenfolge f&#252;r Konstruktoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Initialisierungsreihenfolge für Klassenkonstruktoren hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
## Vergleich der Initialisierungsreihenfolge für Konstruktoren  
 In Managed Extensions for C\+\+ wurden Konstruktoren in der folgenden Reihenfolge initialisiert:  
  
1.  Der Konstruktor der Basisklasse wird aufgerufen, falls vorhanden.  
  
2.  Die Initialisierungsliste der Klasse wird ausgewertet.  
  
3.  Der Codetext des Klassenkonstruktors wird ausgeführt.  
  
 Diese Ausführungsreihenfolge basiert auf den gleichen Konventionen wie bei der systemeigenen C\+\+\-Programmierung.  Die neue Visual C\+\+\-Sprache sieht für CLR\-Klassen die folgende Ausführungsreihenfolge vor:  
  
1.  Die Initialisierungsliste der Klasse wird ausgewertet.  
  
2.  Der Konstruktor der Basisklasse wird aufgerufen, falls vorhanden.  
  
3.  Der Codetext des Klassenkonstruktors wird ausgeführt.  
  
 Beachten Sie, dass diese Änderung nur für CLR\-Klassen gilt; systemeigene Klassen in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] folgen weiterhin den alten Konventionen.  In beiden Fällen setzen sich diese Regeln durch die gesamte Hierarchiekette einer bestimmten Klasse nach oben fort.  
  
 Betrachten Sie das folgende Codebeispiel aus Managed Extensions for C\+\+:  
  
```  
__gc class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
__gc class B : public A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 Gemäß der oben genannten Initialisierungsreihenfolge für Konstruktoren ist die folgende Ausführungsreihenfolge zu erwarten, wenn neue Instanzen der Klasse `B` erstellt werden:  
  
1.  Der Konstruktor der Basisklasse `A` wird aufgerufen.  Der `_n`\-Member wird mit `1` initialisiert.  
  
2.  Die Initialisierungsliste für die Klasse `B` wird ausgewertet.  Der `_m`\-Member wird mit `1` initialisiert.  
  
3.  Der Codetext der Klasse `B` wird ausgeführt.  
  
 Betrachten Sie nun den gleichen Code in der neuen Visual C\+\+\-Syntax:  
  
```  
ref class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
ref class B : A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 Die Ausführungsreihenfolge beim Erstellen neuer Instanzen der Klasse `B` sieht in der neuen Syntax wie folgt aus:  
  
1.  Die Initialisierungsliste für die Klasse `B` wird ausgewertet.  Der `_m`\-Member wird mit `0` initialisiert \(`0` ist der nicht initialisierte Wert des `_m`\-Klassenmembers\).  
  
2.  Der Konstruktor der Basisklasse `A` wird aufgerufen.  Der `_n`\-Member wird mit `1` initialisiert.  
  
3.  Der Codetext der Klasse `B` wird ausgeführt.  
  
 Beachten Sie, dass bei diesen Codebeispielen eine ähnliche Syntax zu unterschiedlichen Ergebnissen führt.  Der Konstruktor der Klasse `B` benötigt zum Initialisieren seines Members einen Wert der Basisklasse `A`.  Der Konstruktor für die Klasse `A` wurde jedoch noch nicht aufgerufen.  Eine derartige Abhängigkeit kann besonders dann riskant sein, wenn die geerbte Klasse auf eine Speicherbelegung oder Ressourcenreservierung im Basisklassenkonstruktor angewiesen ist.  
  
## Was dies für den Wechsel von Managed Extensions for C\+\+ zu Visual C\+\+ 2010 bedeutet  
 Häufig sind die Änderungen an der Ausführungsreihenfolge von Klassenkonstruktoren für den Programmierer transparent, da sich Basisklassen vollkommen anders verhalten als geerbte Klassen.  Wie diese Codebeispiele veranschaulichen, können die Konstruktoren geerbter Klassen jedoch stark betroffen sein, wenn ihre Initialisierungslisten von den Werten der Basisklassenmember abhängen.  Wenn Sie Code aus Managed Extensions for C\+\+ in die neue Syntax umwandeln, sollten Sie solche Konstrukte ggf. in den Textteil des Klassenkonstruktors verschieben, der nachweislich zuletzt ausgeführt wird.  
  
## Siehe auch  
 [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Konstruktoren](../cpp/constructors-cpp.md)   
 [Konstruktorinitialisierer](../misc/constructor-initializers.md)