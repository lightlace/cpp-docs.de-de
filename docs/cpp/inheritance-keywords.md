---
title: "Vererbungsschl&#252;sselw&#246;rter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__multiple_inheritance"
  - "__single_inheritance_cpp"
  - "__virtual_inheritance_cpp"
  - "__virtual_inheritance"
  - "__multiple_inheritance_cpp"
  - "__single_inheritance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__multiple_inheritance-Schlüsselwort [C++]"
  - "__single_inheritance-Schlüsselwort [C++]"
  - "__virtual_inheritance-Schlüsselwort [C++]"
  - "Deklarieren von abgeleiteten Klassen"
  - "Abgeleitete Klassen, Deklarieren"
  - "Vererbung, Deklarieren von abgeleiteten Klassen"
  - "Vererbung, Schlüsselwörter"
  - "Schlüsselwörter [C++], Vererbungsschlüsselwörter"
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Vererbungsschl&#252;sselw&#246;rter
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
```  
  
class [__single_inheritance] class-name; class [__multiple_inheritance] class-name; class [__virtual_inheritance] class-name;  
```  
  
 wobei:  
  
 *Klassenname*  
 Der Name der zu deklarierenden Klasse.  
  
 C\+\+ ermöglicht es Ihnen, vor der Definition der Klasse einen Zeiger auf einen Klassenmember zu deklarieren.  Beispiel:  
  
```  
class S;  
int S::*p;  
```  
  
 Im Code oben wird `p` als Zeiger auf den ganzzahligen Member der Klasse S deklariert.  `class S` ist jedoch noch nicht in diesem Code definiert worden. Er ist nur deklariert.  Wenn der Compiler einen solchen Zeiger erkennt, muss er eine allgemeine Darstellung des Zeigers erzeugen.  Die Größe der Darstellung ist vom angegebenen Vererbungsmodell abhängig.  Es gibt vier Möglichkeiten, ein Vererbungsmodell für den Compiler anzugeben:  
  
-   In der IDE unter **pointer\-to\-member\-Darstellung**  
  
-   Mithilfe des [\/vmg](../build/reference/vmb-vmg-representation-method.md)\-Schalters in der Befehlszeile  
  
-   Verwenden des [pointers\_to\_members](../preprocessor/pointers-to-members.md)\-Pragmas  
  
-   Mithilfe der Vererbungs\-Schlüsselwörter `__single_inheritance`, `__multiple_inheritance` und `__virtual_inheritance`.  Dieses Verfahren steuert das Vererbungsmodell auf Basis einer einzelnen Klasse.  
  
    > [!NOTE]
    >  Wenn Sie stets einen Zeiger auf einen Member einer Klasse deklarieren, nachdem Sie die Klasse definiert haben, ist es nicht erforderlich, eine dieser Optionen zu verwenden.  
  
 Das Deklarieren eines Zeigers auf einen Member einer Klasse vor der Klassendefinition wirkt sich auf die Größe und die Geschwindigkeit der erstellten ausführbaren Datei aus.  Je komplexer die von einer Klasse genutzte Vererbung ist, desto größer sind die Byteanzahl, die für die Darstellung eines Zeigers auf einen Member der Klasse erforderlich ist, und der für die Interpretation des Zeigers erforderliche Code.  Die einfache Vererbung ist am wenigsten komplex und die virtuelle Vererbung ist die komplexeste Vererbung.  
  
 Wenn das obige Beispiel so geändert wird:  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 Unabhängig von Befehlszeilenoptionen oder Pragmas verwenden Zeiger auf Member von `class S` die kleinstmögliche Darstellung.  
  
> [!NOTE]
>  Dieselbe Vorwärtsdeklaration einer pointer\-to\-member\-Klassendarstellung sollte in jeder Übersetzungseinheit auftreten, die Zeiger auf Member dieser Klasse deklariert. Die Deklaration sollte vor der pointer\-to\-member\-Deklaration erfolgen.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)