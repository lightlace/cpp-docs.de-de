---
title: C-Speicherklassen | Microsoft-Dokumentation
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
- static variables, lifetime
- storage classes
- lifetime, variables
- specifiers, storage class
- storage class specifiers, C storage classes
- storage duration
ms.assetid: 893fb929-f7a9-43dc-a0b3-29cb1ef845c1
caps.latest.revision: 9
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
ms.openlocfilehash: f62910c5bd1ede1a54345488896e0abfe6c748b4
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="c-storage-classes"></a>C-Speicherklassen
Die "Speicherklasse" einer Variablen bestimmt, ob das Element eine "globale" oder "lokale" Lebensdauer hat. Diese zwei Angaben zur Lebensdauer werden von C als "static" oder "automatic" aufgerufen. Ein Element mit einer globalen Lebensdauer ist während der gesamten Ausführung des Programms vorhanden und verfügt über einen Wert. Alle Funktionen haben eine globale Lebensdauer.  
  
 Automatischen Variablen oder Variablen mit lokaler Lebensdauer wird jedes Mal neuer Speicherplatz zugeordnet, wenn die Ausführungssteuerung an den Block übergeben wird, in dem sie definiert sind. Wenn die Ausführung zurückkehrt, haben die Variablen keine sinnvollen Werte mehr.  
  
 C stellt die folgenden Speicherklassenspezifizierer bereit:  
  
## <a name="syntax"></a>Syntax  
 *storage-class-specifier*:  
 **auto**  
  
 **register**  
  
 **static**  
  
 **extern**  
  
 **typedef**  
  
 **__declspec** ( *extended-decl-modifier-seq* ) /* Microsoft-spezifisch \*/  
  
 Mit Ausnahme von `__declspec` können Sie in einer Deklaration nur einen *storage-class-specifier* im *declaration-specifier* verwenden. Wenn keine Speicherklassenspezifikation vorhanden ist, erstellen die Deklarationen in einem Block automatische Objekte.  
  
 Elemente, die mit dem **auto**- oder **register**-Spezifizierer deklariert werden, verfügen über eine lokale Lebensdauer. Elemente, die mit dem **static**- oder `extern`-Spezifizierer deklariert werden, verfügen über eine globale Lebensdauer.  
  
 Da sich `typedef` und `__declspec` semantisch von den anderen vier *storage-class-specifier*-Terminalen unterscheiden, werden diese gesondert behandelt. Spezifische Informationen zu `typedef` finden Sie unter [Typedef-Deklarationen](../c-language/typedef-declarations.md). Spezifische Informationen zu `__declspec` finden Sie unter [Erweiterte Speicherklassenattribute](../c-language/c-extended-storage-class-attributes.md).  
  
 Die Platzierung der Variablen- und Funktionsdeklarationen innerhalb der Quelldateien wirkt sich auch auf die Speicherklasse und die Sichtbarkeit aus. Deklarationen außerhalb von sämtlichen Funktionsdefinitionen treten auf "externer Ebene" auf. Deklarationen innerhalb von Funktionsdefinitionen treten auf "interner Ebene" auf.  
  
 Die genaue Bedeutung von jedem Speicherklassenspezifizierer hängt von zwei Faktoren ab:  
  
-   Ob die Deklaration auf der externen oder internen Ebene auftritt  
  
-   Ob das deklarierte Element eine Variable oder eine Funktion ist  
  
 Unter [Speicherklassenspezifizierer für Deklarationen der externen Ebene](../c-language/storage-class-specifiers-for-external-level-declarations.md) und [Speicherklassenspezifizierer für Deklarationen der internen Ebene](../c-language/storage-class-specifiers-for-internal-level-declarations.md) finden Sie eine Beschreibung der *storage-class-specifier*-Terminale in der jeweiligen Deklarationsart und eine Erläuterung des Standardverhaltens, wenn der *storage-class-specifier* in einer Variable weggelassen wird. Unter [Speicherklassenspezifizierer mit Funktionsdeklarationen](../c-language/storage-class-specifiers-with-function-declarations.md) finden Sie eine Erläuterung zu Speicherklassenspezifizierern, die mit Funktionen verwendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)
