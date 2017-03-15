---
title: "2.7.2.6 reduction"
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
ms.assetid: e7630a15-2978-4dbe-a29b-3a46371a0151
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.6 reduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klausel führt eine Verringerung auf den skalaren Variablen *in der Liste Variablen*angezeigt werden, werden mit dem Operator " op aus.  Die Syntax der `reduction`\-Klausel lautet wie folgt:  
  
```  
  
reduction(  
op  
:  
variable-list  
)  
  
```  
  
 Eine Verringerung wird i. d. R. für eine Anweisung mit einem der folgenden Formate angegeben:  
  
```  
  
        x     =  x     op     expr  
x     binop=  expr  
x     =  expr     op     x            (except for subtraction)  
x++  
++x  
x--  
--x  
```  
  
 Dabei gilt:  
  
 *x*  
 Eine der Variablen Reduzierungs in `list`.  
  
 *VariableListe*  
 Eine durch Trennzeichen getrennte Liste von skalaren Variablen Reduzierungs.  
  
 *expr*  
 Ein Ausdruck mit skalarem Typ, der nicht *X*verweist *.*  
  
 `op`  
 Es wurde kein überladener Operator \+, der jedoch ein, \-, &\*, ^, &#124;oder &&&#124;&#124;.  
  
 `binop`  
 Es wurde kein überladener Operator \+, der jedoch ein, \-, &\*, oder ^ &#124;.  
  
 Im Folgenden finden Sie ein Beispiel für die `reduction`\-Klausel:  
  
```  
#pragma omp parallel for reduction(+: a, y) reduction(||: am)  
for (i=0; i<n; i++) {  
   a += b[i];  
   y = sum(y, c[i]);  
   am = am || b[i] == c[i];  
}  
```  
  
 Wie im Beispiel gezeigt, wird möglicherweise ein Operator innerhalb eines Funktionsaufrufs ausgeblendet.  Der Benutzer sollte sorgfältig darauf achten, den der Operator in den `reduction`\-Klausel Reduzierungs Übereinstimmungen mit den Vorgang angegeben hat.  
  
 Obwohl der rechte Operand aus &#124;&#124; Operator hat keine Nebeneffekte in diesem Beispiel, werden sie nicht zulässig, jedoch sollten sorgfältig verwendet werden.  In diesem Kontext ein Nebeneffekt tritt möglicherweise nicht garantiert, dass der während der sequenziellen Ausführung der Schleife ausgeführt, während der parallelen Ausführung.  Dieser Unterschied kann auftreten, da die Ausführungsreihenfolge der Iterationen unbestimmt ist.  
  
 Der Operator wird, um den Anfangswert aller privaten Variablen zu bestimmen, die vom Compiler für die Verringerung und den abschließenden operator zu bestimmen, verwendet werden.  Das Angeben des Operators explizit zugelassen Reduzierungs der Anweisung außerhalb des lexikalischen Wertebereichs des Konstrukts sein.  Eine beliebige Anzahl `reduction`\-Klauseln wird in der Direktive angegeben, aber eine Variable tritt möglicherweise in höchstens einer `reduction`\-Klausel für diese Direktive.  
  
 Eine private Kopie einer Variablen *in der Liste Variablen* , eine für jeden Thread erstellt, als ob die `private`\-Klausel verwendet worden wäre.  Der private Kopie wird entsprechend dem Operator initialisiert \(siehe folgende Tabelle\).  
  
 Am Ende des Bereichs, für den die `reduction`\-Klausel angegeben wurde, wird das ursprüngliche Objekt aktualisiert, um das Ergebnis der Kombination des ursprünglichen Werts mit dem endgültigen Werts aus jeder der private Kopien unter Verwendung des angegebenen Operators angibt.  Die Reduzierungs Operatoren sind alle Subtraktion\) \(außer vereinigend, und der Compiler weist möglicherweise auf die Berechnung des endgültigen Werts neu zu.  \(Mit partiellen Ergebnisse einer Subtraktions reduzierung werden hinzugefügt, um den endgültigen Wert zu bilden.\)  
  
 Der Wert des ursprünglichen Objekts wird endlos wiederholt, wenn der erste Thread die enthaltende \- Klausel erreicht hat und daher bleibt, bis Reduzierungs die Berechnung abgeschlossen ist.  Normalerweise ist die Berechnung am Ende des Konstrukts abgeschlossen. Wenn jedoch die `reduction`\-Klausel in einem Konstrukt verwendet wird, auf dem auch `nowait` angewendet wird, bleibt der Wert des ursprünglichen Objekts endlos wiederholt, bis eine Barrieren Datensynchronisierung durchgeführt wurde, um sicherzustellen, dass alle Threads die `reduction`\-Klausel durchgeführt haben.  
  
 In der folgenden Tabelle sind die Operatoren, die gültig sind und ihre kanonischen Initialisierungswerte auf.  Der tatsächliche Initialisierungswert ist mit dem Datentyp der Reduzierungs variable konsistent.  
  
|Operator|Initialisierung|  
|--------------|---------------------|  
|\+|0|  
|\*|1|  
|\-|0|  
|&|~0|  
|&#124;|0|  
|^|0|  
|&&|1|  
|&#124;&#124;|0|  
  
 Die Einschränkungen zur `reduction`\-Klausel lauten wie folgt:  
  
-   Der Typ der Variablen in der `reduction`\-Klausel muss für den Operator Reduzierungs gültig, außer dass Zeigertypen und Verweistypen sind nicht zulässig.  
  
-   Eine Variable, die in der `reduction`\-Klausel angegeben wird, darf nicht qualifiziertes \- **const**sein.  
  
-   Variablen, die innerhalb eines parallelen Bereichs privat sind oder die in der `reduction`\-Klausel **Ähnlichkeit**\-Direktive angezeigt werden, können nicht in einer `reduction`\-Klausel auf Arbeitsteilungs direktiven angegeben werden, die zum parallelen Konstrukt bindet.  
  
    ```  
    #pragma omp parallel private(y)  
    { /* ERROR - private variable y cannot be specified  
                 in a reduction clause */  
       #pragma omp for reduction(+: y)  
       for (i=0; i<n; i++)  
          y += b[i];  
    }  
  
    /* ERROR - variable x cannot be specified in both  
               a shared and a reduction clause */  
    #pragma omp parallel for shared(x) reduction(+: x)  
    ```