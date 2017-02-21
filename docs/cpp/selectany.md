---
title: "selectany | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "selectany_cpp"
  - "selectany"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec-Schlüsselwort [C++], selectany"
  - "selectany __declspec-Schlüsselwort"
ms.assetid: 9c353017-5a42-4f50-b741-bd13da1ce84d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# selectany
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Weist den Compiler an, dass das deklarierte, globale Datenelement \(Variable oder Objekt\) ein beliebig auswählbares COMDAT \(eine Paketfunktion\) ist.  
  
## Syntax  
  
```  
  
__declspec( selectany ) declarator  
```  
  
## Hinweise  
 Wenn zum Zeitpunkt der Verknüpfung mehrere Definitionen einer COMDAT angezeigt werden, wählt der Linker eine aus und verwirft den Rest.  Wenn die Linkeroption [\/OPT: REF](../build/reference/opt-optimizations.md) \(Optimizations\) ausgewählt wird, erfolgt eine COMDAT\-Eliminierung, um alle unreferenzierten Datenelemente in der Linkerausgabe zu entfernen.  
  
 Konstruktoren und Zuweisung durch globale Funktion oder statische Methoden in der Deklaration erstellen keine Verweise und verhindern die \/OPT: REF\-Eliminierung nicht.  Nebeneffekte von derartigem Code sollten nicht davon abhängen, ob keine weiteren Verweise auf die Daten vorhanden sind.  
  
 Bei die dynamisch initialisierten, globalen Objekte wird `selectany` den Initialisierungscode eines Objekts, auf das nicht verwiesen wird, verwerfen.  
  
 Ein globales Datenelement kann normalerweise nur einmal in einem EXE\- bzw. DLL\-Projekt initialisiert werden.  `selectany` kann beim Initialisieren von globalen Daten verwendet werden, die durch Header definiert sind, wenn derselbe Header in mehr als einer Quelldatei angezeigt wird.  `selectany` ist im C\- und im C\+\+\-Compiler verfügbar.  
  
> [!NOTE]
>  `selectany` kann nur auf die tatsächliche Initialisierung globaler Datenelemente angewendet werden, die extern sichtbar sind.  
  
## Beispiel  
 Dieser Code zeigt die Verwendung des `selectany`\-Attributs:  
  
```  
//Correct - x1 is initialized and externally visible   
__declspec(selectany) int x1=1;  
  
//Incorrect - const is by default static in C++, so   
//x2 is not visible externally (This is OK in C, since  
//const is not by default static in C)  
const __declspec(selectany) int x2 =2;  
  
//Correct - x3 is extern const, so externally visible  
extern const __declspec(selectany) int x3=3;  
  
//Correct - x4 is extern const, so it is externally visible  
extern const int x4;  
const __declspec(selectany) int x4=4;  
  
//Incorrect - __declspec(selectany) is applied to the uninitialized  
//declaration of x5  
extern __declspec(selectany) int x5;  
  
// OK: dynamic initialization of global object  
class X {  
public:  
X(int i){i++;};  
int i;  
};  
  
__declspec(selectany) X x(1);  
```  
  
## Beispiel  
 Dieser Code zeigt, wie das `selectany`\-Attribut verwendet wird, um die COMDAT\-Faltung der Daten zu gewährleisten, wenn Sie auch die [\/OPT:ICF](../build/reference/opt-optimizations.md)\-Linkeroption verwenden.  Beachten Sie, dass Daten mit `selectany` markiert und in einen \(schreibgeschützten\) **const**\-Abschnitt eingefügt werden müssen.  Sie müssen den schreibgeschützten Abschnitt explizit angeben.  
  
```  
// selectany2.cpp  
// in the following lines, const marks the variables as read only  
__declspec(selectany) extern const int ix = 5;  
__declspec(selectany) extern const int jx = 5;  
int main() {  
   int ij;  
   ij = ix + jx;  
}  
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [\_\_declspec](../cpp/declspec.md)   
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)