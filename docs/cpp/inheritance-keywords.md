---
title: "Vererbungsschlüsselwörter | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __multiple_inheritance
- __single_inheritance_cpp
- __virtual_inheritance_cpp
- __virtual_inheritance
- __multiple_inheritance_cpp
- __single_inheritance
dev_langs: C++
helpviewer_keywords:
- __single_inheritance keyword [C++]
- declaring derived classes [C++]
- keywords [C++], inheritance keywords
- __multiple_inheritance keyword [C++]
- __virtual_inheritance keyword [C++]
- inheritance, declaring derived classes
- derived classes [C++], declaring
- inheritance, keywords
ms.assetid: bb810f56-7720-4fea-b8b6-9499edd141df
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 442e8958b1d2201d7261242bd9cd90da29a60a62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="inheritance-keywords"></a>Vererbungsschlüsselwörter
**Microsoft-spezifisch**  
  
```  
class [__single_inheritance] class-name;
class [__multiple_inheritance] class-name;
class [__virtual_inheritance] class-name;  
```  
  
 Dabei gilt:  
  
 *Klassenname*  
 Der Name der zu deklarierenden Klasse.  
  
 C++ ermöglicht es Ihnen, vor der Definition der Klasse einen Zeiger auf einen Klassenmember zu deklarieren. Zum Beispiel:  
  
```  
class S;  
int S::*p;  
```  
  
 Im obigen Code `p` wird als Zeiger auf den ganzzahligen Member der Klasse s deklariert Allerdings `class S` wurde noch nicht in diesem Code definiert wurde es nur deklariert wurde. Wenn der Compiler einen solchen Zeiger erkennt, muss er eine allgemeine Darstellung des Zeigers erzeugen. Die Größe der Darstellung ist vom angegebenen Vererbungsmodell abhängig. Es gibt vier Möglichkeiten, ein Vererbungsmodell für den Compiler anzugeben:  
  
-   In der IDE unter **Pointer-to-Member-Darstellung**  
  
-   In der Befehlszeile unter Verwendung der [/vmg](../build/reference/vmb-vmg-representation-method.md) wechseln  
  
-   Mithilfe der [Pointers_to_members](../preprocessor/pointers-to-members.md) Pragma  
  
-   Mithilfe der Vererbungs-Schlüsselwörter `__single_inheritance`, `__multiple_inheritance` und `__virtual_inheritance`. Dieses Verfahren steuert das Vererbungsmodell auf Basis einer einzelnen Klasse.  
  
    > [!NOTE]
    >  Wenn Sie stets einen Zeiger auf einen Member einer Klasse deklarieren, nachdem Sie die Klasse definiert haben, ist es nicht erforderlich, eine dieser Optionen zu verwenden.  
  
 Das Deklarieren eines Zeigers auf einen Member einer Klasse vor der Klassendefinition wirkt sich auf die Größe und die Geschwindigkeit der erstellten ausführbaren Datei aus. Je komplexer die von einer Klasse genutzte Vererbung ist, desto größer sind die Byteanzahl, die für die Darstellung eines Zeigers auf einen Member der Klasse erforderlich ist, und der für die Interpretation des Zeigers erforderliche Code. Die einfache Vererbung ist am wenigsten komplex und die virtuelle Vererbung ist die komplexeste Vererbung.  
  
 Wenn das obige Beispiel so geändert wird:  
  
```  
class __single_inheritance S;  
int S::*p;  
```  
  
 Unabhängig von Befehlszeilenoptionen oder Pragmas verwenden Zeiger auf Member von `class S` die kleinstmögliche Darstellung.  
  
> [!NOTE]
>  Dieselbe Vorwärtsdeklaration einer pointer-to-member-Klassendarstellung sollte in jeder Übersetzungseinheit auftreten, die Zeiger auf Member dieser Klasse deklariert. Die Deklaration sollte vor der pointer-to-member-Deklaration erfolgen.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../cpp/keywords-cpp.md)