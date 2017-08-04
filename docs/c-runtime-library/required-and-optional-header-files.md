---
title: Erforderliche und optionale Headerdateien | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.headers
dev_langs:
- C++
helpviewer_keywords:
- include files, required in run time
- header files, required in run time
ms.assetid: f64d0bf5-e2c3-4b42-97d0-443b3d901d9f
caps.latest.revision: 7
author: corob-msft
ms.author: corob
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
ms.openlocfilehash: 82f325ec2a8e928d721b3b3f16683961634365e2
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="required-and-optional-header-files"></a>Erforderliche und optionale Headerdateien
Die Beschreibung jeder Laufzeitroutine enthält eine Liste der erforderlichen und optionalen Include- oder Headerdateien (.H) für diese Routine. Erforderliche Headerdateien müssen eingeschlossen werden, um die Funktionsdeklaration für die Routine abzurufen, oder eine Definition, die von einer anderen, intern aufgerufenen Routine verwendet wird. Optionale Headerdateien werden in der Regel eingeschlossen, um vordefinierte Konstanten, Typdefinitionen oder Inlinemakros zu nutzen. Die folgende Tabelle enthält einige Beispiele für die Inhalte optionaler Headerdateien:  
  
|Definition|Beispiel|  
|----------------|-------------|  
|Makrodefinition|Wenn eine Bibliotheksroutine als Makro implementiert wird, kann sich die Makrodefinition in einer anderen Headerdatei als der Headerdatei für die ursprüngliche Routine befinden. Beispielsweise ist das `_toupper`-Makro in der Headerdatei CTYPE.H definiert, die Funktion `toupper` hingegen in STDLIB.H.|  
|Vordefinierte Konstante|Viele Bibliotheksroutinen verweisen auf Konstanten, die in Headerdateien definiert sind. Beispielsweise verwendet die `_open`-Routine Konstanten wie z.B. `_O_CREAT`, die in der Headerdatei FCNTL.H definiert ist.|  
|Typdefinition|Einige Bibliotheksroutinen geben eine Struktur zurück oder übernehmen eine Struktur als Argument. Routinen zur Datenstromeingabe/-ausgabe verwenden z.B. eine Struktur vom Typ `FILE`, die in STDIO.H definiert ist.|  
  
 Die Laufzeitbibliothek-Headerdateien bieten Funktionsdeklarationen im empfohlenen Format des ANSI/ISO-C-Standards. Der Compiler führt eine Typüberprüfung für alle Routinenverweise durch, die nach der zugeordneten Funktionsdeklaration erfolgt. Funktionsdeklarationen sind besonders wichtig für Routinen, die einen Wert eines bestimmten Typs außer `int` zurückgeben; dies ist die Standardeinstellung. Bei Routinen, die den jeweiligen Rückgabewert nicht in ihrer Deklaration angeben, setzt der Compiler die Rückgabe von `int` voraus, was zu unerwarteten Ergebnissen führen kann. Weitere Informationen finden Sie unter [Typüberprüfung](../c-runtime-library/type-checking-crt.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
