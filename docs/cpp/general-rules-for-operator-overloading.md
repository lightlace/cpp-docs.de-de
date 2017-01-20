---
title: "Allgemeine Regeln f&#252;r die &#220;berladung von Operatoren"
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
  - "Operatoren überladen, Regeln"
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Allgemeine Regeln f&#252;r die &#220;berladung von Operatoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Regeln schränken die Art und Weise ein, wie überladene Operatoren implementiert werden.  Allerdings gelten sie nicht für die Operatoren [new](../cpp/new-operator-cpp.md) und [delete](../cpp/delete-operator-cpp.md), die separat behandelt werden.  
  
-   Sie können keine neuen Operatoren, wie etwa \*\*, definieren.  
  
-   Sie können die Bedeutung von Operatoren nicht neu definieren, wenn sie auf integrierte Datentypen angewendet werden.  
  
-   Überladene Operatoren müssen entweder eine nicht statische Klassenmemberfunktion oder eine globale Funktion sein.  Eine globale Funktion, die auf private oder geschützte Klassenmember zugreifen muss, muss als Friend dieser Klasse deklariert sein.  Eine globale Funktion muss mindestens ein Argument annehmen, das vom Klassen\- oder Aufzählungstyp ist, oder das ein Verweis auf einen Klassen\- oder Aufzählungstyp ist.  Beispiel:  
  
    ```  
    // rules_for_operator_overloading.cpp  
    class Point  
    {  
    public:  
        Point operator<( Point & );  // Declare a member operator   
                                     //  overload.  
        // Declare addition operators.  
        friend Point operator+( Point&, int );  
        friend Point operator+( int, Point& );  
    };  
  
    int main()  
    {  
    }  
    ```  
  
     Das vorhergehende Codebeispiel deklariert den Less Than\-Operator als Memberfunktion. Allerdings werden die Additionsoperatoren als globale Funktionen deklariert, die Friend\-Zugriff haben.  Beachten Sie, dass mehr als eine Implementierung für einen angegebenen Operator bereitgestellt werden kann.  Im Fall des vorhergehenden Additionsoperators werden die beiden Implementierungen bereitgestellt, um Kommutativität zu ermöglichen.  Es ist ebenso wahrscheinlich, dass Operatoren, die `Point` `Point`, `int` einem `Point` usw. hinzufügen, implementiert werden könnten.  
  
-   Operatoren unterliegen der Priorität, Gruppierung und Anzahl von Operanden, die durch ihre typische Verwendung mit integrierten Typen vorgegeben werden.  Daher gibt es keine Möglichkeit, das Konzept zu beschreiben, gemäß dem 2 und 3 einem Objekt vom Typ `Point` hinzugefügt werden, wobei erwartet wird, dass 2 der *x*\-Koordinate hinzugefügt und 3 der *y*\-Koordinate hinzugefügt wird.  
  
-   Unäre Operatoren, die als Memberfunktionen deklariert werden, akzeptieren keine Argumente. Wenn sie als globale Funktionen deklariert werden, nehmen sie ein Argument an.  
  
-   Binäre Operatoren, die als Memberfunktionen deklariert werden, akzeptieren ein Argument. Wenn sie als globale Funktionen deklariert werden, nehmen sie zwei Argumente an.  
  
-   Wenn ein Operator sowohl als unärer als auch als binärer Operator verwendet werden kann \(**&**, **\***, **\+** und **\-**\), können Sie jede Verwendung separat überladen.  
  
-   Überladene Operatoren können keine Standardargumente haben.  
  
-   Alle überladenen Operatoren außer der Zuweisung \(`operator=`\) werden von abgeleiteten Klassen geerbt.  
  
-   Das erste Argument für mit Memberfunktionen überladene Operatoren weist immer den Klassentyp des Objekts auf, für das der Operator aufgerufen wird \(die Klasse, in der der Operator deklariert ist, oder eine Klasse, die von dieser Klasse abgeleitet ist\).  Es werden keine Konvertierungen für das erste Argument bereitgestellt.  
  
 Beachten Sie, dass die Bedeutung aller Operatoren vollständig geändert werden kann.  Das schließt die Bedeutung des address\-of\-Operators \(**&**\), des Zuweisungsoperators \(**\=**\) und des function\-call\-Operators mit ein.  Auch Identitäten, auf denen integrierte Typen basieren können, können mithilfe der Operatorüberladung geändert werden.  Beispielsweise sind die folgenden vier Anweisungen normalerweise gleichwertig, wenn sie vollständig ausgewertet werden:  
  
```  
var = var + 1;  
var += 1;  
var++;  
++var;  
```  
  
 Klassentypen, die Operatoren überladen, können nicht auf dieser Identität basieren.  Darüber hinaus sind einige der Anforderungen, die für die Verwendung dieser Operatoren für grundlegende Typen gelten, für überladene Operatoren weniger strikt.  Zum Beispiel erfordert der Additions\-\/Zuweisungsoperator, `+=`, dass der linke Operand ein L\-Wert ist, wenn er auf grundlegende Typen angewendet wird. Wenn der Operator überladen wird, gibt es keine solche Anforderung.  
  
> [!NOTE]
>  Aus Gründen der Konsistenz ist es oft am besten, beim Definieren überladener Operatoren das Modell der integrierten Typen zu befolgen.  Wenn sich die Semantik eines überladenen Operators deutlich von seiner Bedeutung in anderen Kontexten unterscheidet, kann das eher verwirrend als nützlich sein.  
  
## Siehe auch  
 [Überladen von Operatoren](../cpp/operator-overloading.md)