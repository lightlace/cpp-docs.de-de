---
title: Explizite Instanziierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb2f1c14028820525748c8e770a7263eedd3099f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405200"
---
# <a name="explicit-instantiation"></a>Explizite Instantiierung
Mit expliziter Instanziierung können Sie eine Instanziierung einer auf Vorlagen basierenden Klasse oder Funktion erstellen, ohne sie tatsächlich im Code zu verwenden. Da dies nützlich ist, wenn Sie Bibliotheksdateien (LIB-Dateien) erstellen, die Vorlagen zur Verteilung verwenden, werden nicht instanziierte Vorlagendefinitionen nicht in Objektdateien (OBJ-Dateien) abgelegt.  
  
 Dieser Code explizit instanziiert `MyStack` für **Int** -Variablen und sechs Elemente:  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Diese Anweisung erstellt eine Instanziierung von `MyStack`, ohne Speicher für ein Objekt zu reservieren. Code wird für alle Member generiert.  
  
 Die nächste Zeile instanziiert explizit nur die Konstruktormemberfunktion:  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Sie können Funktionsvorlagen explizit instanziieren, indem ein bestimmtes Typargument, um sie erneut zu deklarieren, wie im Beispiel in [Funktionsvorlageninstanziierung](../cpp/function-template-instantiation.md).  
  
 Sie können die **"extern"** Schlüsselwort, um zu verhindern, dass die automatische Instanziierung von Membern. Zum Beispiel:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 Entsprechend können Sie bestimmte Member als nicht instanziiert und extern kennzeichnen:  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Sie können die **"extern"** Schlüsselwort, um zu verhindern, dass den Compiler generiert den gleichen Instanziierungscode in mehr als einem Objektmodul. Sie müssen die Vorlagenfunktion instanziieren, indem Sie die angegebenen expliziten Vorlagenparameter in mindestens einem verknüpften Modul verwenden, wenn die Funktion aufgerufen wird. Andernfalls erhalten Sie einen Linkerfehler, wenn das Programm erstellt wird.  
  
> [!NOTE]
>  Die **"extern"** Schlüsselwort in der Spezialisierung gilt nur für Memberfunktionen, die außerhalb des Texts der Klasse definiert. Die Funktionen, die in der Klassendeklaration definiert werden, gelten als Inlinefunktionen und werden immer instanziiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)