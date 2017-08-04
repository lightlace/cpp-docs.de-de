---
title: C-Enumerationsdeklarationen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- declarations, enumerations
- define directive (#define), alternative to
- enumerators, declaring
- '#define directive, alternative to'
- named constants, enumeration declarations
- declaring enumerations
ms.assetid: bd18f673-4dda-4bc1-92fd-d1ce10074910
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 90d3b0837adb2bd646ef39f4898377c41a030a81
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="c-enumeration-declarations"></a>C-Enumerationsdeklarationen
Eine Enumeration besteht aus einem Satz von benannten ganzzahligen Konstanten. Die Deklaration eines Enumerationstyps gibt den Namen des (optionalen) Enumerationstags an und definiert den Satz benannter ganzzahliger Bezeichner (bezeichnet als "Enumerationssatz", "Enumeratorkonstanten", "Enumeratoren" oder "Member"). Eine Variable mit Enumerationstyp speichert einen der Werte des Enumerationssatzes, der durch diesen Typ definiert ist.  
  
 Variablen des Typs `enum` können in Indizierungsausdrücken und als Operanden aller arithmetischen und relationalen Operatoren verwendet werden. Enumerationen bieten eine Alternative zur Präprozessordirektive `#define` und bieten den Vorteil, dass die Werte für Sie generiert werden und normalen Bereichsregeln folgen.  
  
 In ANSI C weisen die Ausdrücke, die den Wert einer Enumeratorkonstante definieren, immer den `int`-Typ auf. Folglich ist der einer Enumerationsvariable zugeordnete Speicher der für einen einzelnen `int`-Wert benötigte Speicher. Eine Enumerationskonstante oder ein Wert des enumerierten Typs kann überall dort verwendet werden, wo die Programmiersprache C einen ganzzahligen Ausdruck gestattet.  
  
## <a name="syntax"></a>Syntax  
 *enum-specifier*:  
 **enum**  *identifier* opt**{** *enumerator-list* **}**  
  
 **enum**  *identifier*  
  
 Der optionale Wert *identifier* benennt den von *enumerator-list* definierten Enumerationstyp. Dieser Bezeichner wird oft als „Tag“ der Enumeration bezeichnet, die von der Liste angegeben wird. Ein Typspezifizierer der Art  
  
```  
  
enum  
identifier  
{  
enumerator-list  
}  
  
```  
  
 deklariert *identifier* als Tag der Enumeration, die vom *enumerator-list*-Nichtterminal spezifiziert wird. Der „Enumeratorinhalt“ wird von *enumerator-list* definiert. Nachfolgend wird *enumerator-list* ausführlich beschrieben.  
  
 Falls die Deklaration eines Tags sichtbar ist, geben nachfolgende Deklarationen, die das Tag verwenden, *enumerator-list* jedoch weglassen, den zuvor deklarierten enumerierten Typ an. Das Tag muss auf einen definierten Enumerationstyp verweisen, der sich im aktuellen Bereich befindet. Da der Enumerationstyp an einer anderen Stelle definiert ist, wird *enumerator-list* in dieser Deklaration nicht angezeigt. Deklarationen von Typen, die aus Enumerationen abgeleitet sind, und `typedef`-Deklarationen für Enumerationstypen können das Enumerationstag vor der Definition des Enumerationstyps verwenden.  
  
## <a name="syntax"></a>Syntax  
 *enumerator-list*:  
 *enumerator*  
  
 *enumerator-list* **,**  `enumerator`  
  
 `enumerator`:  
 *enumeration-constant*  
  
 *enumeration-constant*  **=**  *constant-expression*  
  
 *enumeration-constant*:  
 *identifier*  
  
 Jeder *enumeration-constant*-Wert in *enumeration-list* benennt einen Wert des Enumerationssatzes. Standardmäßig wird der erste *enumeration-constant*-Wert mit dem Wert 0 verknüpft. Der folgende *enumeration-constant*-Listeneintrag wird mit dem Wert von ( *constant-expression* + 1) verknüpft, außer er wird explizit einem anderen Wert zugeordnet. Der Name von *enumeration-constant* entspricht dessen Wert.  
  
 Sie können mit *enumeration-constant = constant-expression* die Standardabfolge der Werte überschreiben. Wird also *enumeration-constant = constant-expression* in *enumerator-list* angezeigt, wird *enumeration-constant* dem Wert zugeordnet, der von *constant-expression* bereitgestellt wird. *constant-expression* muss den `int`-Typ aufweisen und kann negativ sein.  
  
 Die folgenden Regeln gelten für Member eines Enumerationssatzes:  
  
-   Ein Enumerationssatz kann doppelte konstante Werte enthalten. Beispielsweise könnten Sie den Wert 0 für zwei verschiedene Bezeichner mit den Namen `null` und `zero` im gleichen Satz zuweisen.  
  
-   Die Bezeichner in der Enumerationsliste müssen sich von anderen Bezeichnern im gleichen Bereich mit der gleichen Sichtbarkeit – das schließt gewöhnliche Variablennamen und Bezeichner in anderen Enumerationslisten ein – unterscheiden.  
  
-   Enumerationstags folgen normalen Bereichsregeln. Sie müssen sich von anderen Enumerations-, Struktur- und Union-Tags mit derselben Sichtbarkeit unterscheiden.  
  
## <a name="examples"></a>Beispiele  
 Diese Beispiele veranschaulichen Enumerationsdeklarationen:  
  
```  
enum DAY            /* Defines an enumeration type    */  
{  
    saturday,       /* Names day and declares a       */  
    sunday = 0,     /* variable named workday with    */   
    monday,         /* that type                      */  
    tuesday,  
    wednesday,      /* wednesday is associated with 3 */  
    thursday,  
    friday  
} workday;  
```  
  
 Der Wert 0 wird standardmäßig `saturday` zugeordnet. Der Bezeichner `sunday` wird explizit auf 0 festgelegt. Den verbleibenden Bezeichnern werden standardmäßig die Werte 1 bis 5 zugewiesen.  
  
 In diesem Beispiel wird ein Wert aus dem `DAY`-Satz der Variable `today` zugewiesen.  
  
```  
enum DAY today = wednesday;  
```  
  
 Beachten Sie, dass der Name der Enumerationskonstante zum Zuweisen des Werts verwendet wird. Da zuvor der Enumerationstyp `DAY` deklariert wurde, ist nur das Enumerationstag `DAY` erforderlich.  
  
 Um einen ganzzahligen Wert explizit der Variable des enumerierten Datentyps zuzuweisen, verwenden Sie eine Typumwandlung:  
  
```  
workday = ( enum DAY ) ( day_value - 1 );  
```  
  
 Diese Umwandlung ist in C empfohlen, aber nicht erforderlich.  
  
```  
enum BOOLEAN  /* Declares an enumeration data type called BOOLEAN */  
{  
    false,     /* false = 0, true = 1 */  
    true   
};   
  
enum BOOLEAN end_flag, match_flag; /* Two variables of type BOOLEAN */  
```  
  
 Diese Deklaration kann auch so angegeben werden:  
  
```  
enum BOOLEAN { false, true } end_flag, match_flag;\  
```  
  
 Oder so:  
  
```  
enum BOOLEAN { false, true } end_flag;  
enum BOOLEAN match_flag;  
```  
  
 Ein Beispiel mit diesen Variablen könnte folgendermaßen aussehen:  
  
```  
if ( match_flag == false )  
    {  
     .  
     .   /* statement */   
     .  
    }  
    end_flag = true;  
```  
  
 Auch unbenannte Enumeratordatentypen können deklariert werden. Der Name des Datentyps wird weggelassen, aber Variablen lassen sich deklarieren. Die Variable `response` ist eine Variable des definierten Typs:  
  
```  
enum { yes, no } response;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Enumerationen](../cpp/enumerations-cpp.md)
