---
title: Deklaratoren und Variablendeklarationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaring variables, declarators
- declarators, definition
- declaring variables, declaration statements
ms.assetid: 5fd67a6a-3a6a-4ec9-b257-3f7390a48d40
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a5ec2cf7984940421726dd0197dff4cf6d5ea0c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200358"
---
# <a name="declarators-and-variable-declarations"></a>Deklaratoren und Variablendeklarationen
Im folgenden Abschnitt wird die Form und Bedeutung von Deklarationen für die Variablentypen in dieser Liste beschrieben. Insbesondere wird in den übrigen Abschnitten erklärt, wie Sie Folgendes deklarieren:  
  
|Variablentyp|Beschreibung |  
|----------------------|-----------------|  
|[Einfache Variablen](../c-language/simple-variable-declarations.md)|Einzelwertvariablen vom Typ "Ganzzahl" oder "Gleitkomma"|  
|[Arrays](../c-language/array-declarations.md)|Variablen, die aus einer Auflistung von Elementen mit demselben Typ bestehen|  
|[Zeiger](../c-language/pointer-declarations.md)|Variablen, die auf andere Variablen zeigen und die Speicherorte anderer Variablen (in Form von Adressen) anstelle von Werten enthalten|  
|[Enumerationsvariablen](../c-language/c-enumeration-declarations.md)|Einfache Variablen mit ganzzahligem Typ, die einen Wert aus einem Satz benannter ganzzahliger Konstanten enthalten|  
|[Strukturen](../c-language/structure-declarations.md)|Variablen, die aus einer Auflistung von Werten bestehen, die unterschiedliche Typen aufweisen können|  
|[Unions](../c-language/union-declarations.md)|Variablen, die aus mehreren Werten unterschiedlichen Typs bestehen, die denselben Speicherplatz belegen|  
  
 Ein Deklarator ist der Teil einer Deklaration, der den Namen angibt, der im Programm eingefügt werden soll. Dies kann Modifizierer wie <strong>\*</strong> (pointer-to) sowie jegliche Microsoft-Schlüsselwörter für die Aufrufkonvention einschließen.  
  
 **Microsoft-spezifisch**  
  
 Im Deklarator  
  
```  
__declspec(thread) char *var;  
```  
  
 ist `char` der Typspezifizierer, `__declspec(thread)` und `*` sind die Modifizierer und `var` ist der Name des Bezeichners.  
  
 **Ende Microsoft-spezifisch**  
  
 Sie verwenden Deklaratoren, um Wertarrays, Zeiger auf Werte und Funktionen, die Werte eines angegebenen Typs zurückgeben, zu deklarieren. Deklaratoren kommen in den Array- und Zeigerdeklarationen vor, die weiter unten in diesem Abschnitt beschrieben werden.  
  
## <a name="syntax"></a>Syntax  
 *declarator*:  
 &nbsp;&nbsp;*pointer*<sub>-Opt</sub> *direct-declarator*  
  
 *direct-declarator*:  
 &nbsp;&nbsp;*identifier*  
 &nbsp;&nbsp;**(** *declarator* **)**  
 &nbsp;&nbsp;*direct-declarator* **[** *constant-expression*<sub>-Opt</sub> **]**  
 &nbsp;&nbsp;*direct-declarator* **(** *parameter-type-list* **)**  
 &nbsp;&nbsp;*direct-declarator* **(** *identifier-list*<sub>-Opt</sub> **)**  
  
 *pointer*:  
 &nbsp;&nbsp;<strong>\*</strong> *type-qualifier-list*<sub>-Opt</sub>  
 &nbsp;&nbsp;<strong>\*</strong> *type-qualifier-list*<sub>-Opt</sub> *pointer*  
  
 *type-qualifier-list*:  
 &nbsp;&nbsp;*type-qualifier*  
 &nbsp;&nbsp;*type-qualifier-list type-qualifier*  
  
> [!NOTE]
>  Informationen zur Syntax für *declaration* finden Sie in der [Übersicht über Deklarationen](../c-language/overview-of-declarations.md). Informationen zur Syntax, die auf einen *declarator* verweist, finden Sie unter [Zusammenfassung der C-Sprachsyntax](../c-language/c-language-syntax-summary.md).  
  
 Wenn ein Deklarator aus einem unveränderten Bezeichner besteht, hat das deklarierte Element einen Basistyp. Wenn ein Sternchen (<strong>\*</strong>) auf der linken Seite eines Bezeichners steht, wird der Typ in einen Zeigertyp geändert. Wenn auf den Bezeichner eckige Klammern (**[ ]**) folgen, wird der Typ in einen Arraytyp geändert. Wenn auf den Bezeichner Klammern folgen, wird der Typ in einen Funktionstyp geändert. Weitere Informationen zum Interpretieren der Rangfolge in den Deklarationen finden Sie unter [Interpretieren von komplexeren Deklaratoren](../c-language/interpreting-more-complex-declarators.md).  
  
 Jeder Deklarator deklariert mindestens einen Bezeichner. Ein Deklarator muss einen Typspezifizierer enthalten, um eine vollständige Deklaration zu sein. Der Typspezifizierer gibt den Typ der Elemente eines Arraytyps, den Typ des von einem Zeigertyp angesprochenen Objekts oder den Rückgabetyp einer Funktion an.  
  
 [Array](../c-language/array-declarations.md)- und [Zeiger](../c-language/pointer-declarations.md)-Deklarationen werden weiter unten in diesem Abschnitt ausführlicher beschrieben. Die folgenden Beispiele veranschaulichen ein paar einfache Formen von Deklaratoren:  
  
```  
int list[20]; // Declares an array of 20 int values named list  
char *cp;     // Declares a pointer to a char value  
double func( void ); // Declares a function named func, with no   
                     // arguments, that returns a double value  
int *aptr[10] // Declares an array of 10 pointers  
```  
  
 **Microsoft-spezifisch**  
  
 Der Microsoft C-Compiler lässt eine unbeschränkte Anzahl von Deklaratoren zu, die einen arithmetischen, Struktur- oder Union-Typ ändern können. Die Anzahl wird nur durch den verfügbaren Speicher beschränkt.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)