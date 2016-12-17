---
title: "Gewusst wie: Definieren und Verarbeiten von Enumerationen in C++/CLI"
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
  - "enum-Klasse, Angeben von zugrunde liegenden Typen"
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
caps.latest.revision: 13
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Definieren und Verarbeiten von Enumerationen in C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Thema werden Enumerationen in C\+\+\/CLI.  
  
## Angeben des zugrunde liegenden Typs von enum  
 Standardmäßig ist der zugrunde liegende Typ einer Enumeration `int`.  Sie können jedoch den Typ angeben, mit oder ohne Vorzeichen von `int`, `short`, `long`, `__int32` oder `__int64` sein Formulare.  Sie können `char` auch verwenden.  
  
```  
// mcppv2_enum_3.cpp  
// compile with: /clr  
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};  
  
int main() {  
   // fully qualified names, enumerator not injected into scope  
   day_char d = day_char::sun, e = day_char::mon;  
   System::Console::WriteLine(d);  
   char f = (char)d;  
   System::Console::WriteLine(f);  
   f = (char)e;  
   System::Console::WriteLine(f);  
   e = day_char::tue;  
   f = (char)e;  
   System::Console::WriteLine(f);  
}  
```  
  
 **Ausgabe**  
  
  **Sonne**  
**0**  
**1**  
**2**   
## Wie zwischen verwalteten und Standardenumerationen konvertiert  
 Es gibt keine Standardkonvertierung zwischen einer Enumeration und einen ganzzahligen Typ; eine Umwandlung ist erforderlich.  
  
```  
// mcppv2_enum_4.cpp  
// compile with: /clr  
enum class day {sun, mon, tue, wed, thu, fri, sat};  
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum  
  
int main() {  
   day a = day::sun;  
   day2 = sun;  
   if ((int)a == day2)  
   // or...  
   // if (a == (day)day2)  
      System::Console::WriteLine("a and day2 are the same");  
   else  
      System::Console::WriteLine("a and day2 are not the same");  
}  
```  
  
 **Ausgabe**  
  
  **a und day2 sind gleich**   
## Operatoren und Enumerationen  
 Die folgenden Operatoren sind auf Enumerationen in C\+\+\/CLI gültig:  
  
|Operator|  
|--------------|  
|\=\= \!\= \< \> \<\= \>\=|  
|\+ \-|  
|&#124; ^ & ~|  
|\+\+ \-\-|  
|sizeof|  
  
 Operatoren &#124; &#124; ^ & C\/C\+\+\-Anwendung \- werden nur für Enumerationen mit ganzzahligen zugrunde liegenden Typen, einschließlich bool nicht definiert.  Beide Operanden müssen vom Enumerationstyp sein.  
  
 Der Compiler führt nicht statische oder dynamische Überprüfung des Ergebnisses eines Enumerationsvorgangs; ein Vorgang kann keinen Wert im Bereich von den gültigen Enumeratoren der Enumeration.  
  
> [!NOTE]
>  C\+\+11 stellt Enumerationsklassentypen in nicht verwaltetem Code bereit, der deutlich anders als verwaltete Enumerationsklassen in C\+\+\/CLI sind.  Insbesondere unterstützt der Klassentyp der Enumeration C\+\+11 dieselben Operatoren nicht wie der verwaltete Enumerationsklassentyp in C\+\+\/CLI, und C\+\+\/CLI\-Quellcode muss einen Barrierefreiheitsspezifizierer in verwalteten Enumerationsklassendeklarationen bereitstellen, um sie von nicht verwaltetem Klassendeklarationen der Enumeration zu unterscheiden \(C\+\+11\).  Weitere Informationen zu Klassen in C\+\+\/CLI Enumeration, C\+\+\/CX, und C\+\+11, finden Sie unter [enum class](../windows/enum-class-cpp-component-extensions.md).  
  
```  
// mcppv2_enum_5.cpp  
// compile with: /clr  
private enum class E { a, b } e, mask;  
int main() {  
   if ( e & mask )   // C2451 no E->bool conversion  
      ;  
  
   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)  
      ;  
  
   if ( ( e & mask ) != E() )   // OK  
      ;  
}  
```  
  
```  
// mcppv2_enum_6.cpp  
// compile with: /clr  
private enum class day : int {sun, mon};  
enum : bool {sun = true, mon = false} day2;  
  
int main() {  
   day a = day::sun, b = day::mon;  
   day2 = sun;  
  
   System::Console::WriteLine(sizeof(a));  
   System::Console::WriteLine(sizeof(day2));  
   a++;  
   System::Console::WriteLine(a == b);  
}  
```  
  
 **Ausgabe**  
  
  **4**  
**1**  
**True**   
## Siehe auch  
 [enum class](../windows/enum-class-cpp-component-extensions.md)