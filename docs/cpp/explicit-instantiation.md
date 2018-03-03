---
title: Explizite Instanziierung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- templates, instantiation
- explicit instantiation
- instantiation, explicit
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e272652ecc82b65d0251194f17a746ddde58fcc1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="explicit-instantiation"></a>Explizite Instantiierung
Mit expliziter Instanziierung können Sie eine Instanziierung einer auf Vorlagen basierenden Klasse oder Funktion erstellen, ohne sie tatsächlich im Code zu verwenden. Da dies nützlich ist, wenn Sie Bibliotheksdateien (LIB-Dateien) erstellen, die Vorlagen zur Verteilung verwenden, werden nicht instanziierte Vorlagendefinitionen nicht in Objektdateien (OBJ-Dateien) abgelegt.  
  
 Dieser Code instanziiert `MyStack` explizit für `int`-Variablen und sechs Elemente:  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Diese Anweisung erstellt eine Instanziierung von `MyStack`, ohne Speicher für ein Objekt zu reservieren. Code wird für alle Member generiert.  
  
 Die nächste Zeile instanziiert explizit nur die Konstruktormemberfunktion:  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Funktionsvorlagen können explizit instanziiert werden, mithilfe eines bestimmten Typarguments, erneut deklarieren, wie im Beispiel gezeigt [Funktionsvorlageninstanziierung](../cpp/function-template-instantiation.md).  
  
 Sie können das `extern`-Schlüsselwort verwenden, um die automatische Instanziierung von Membern zu verhindern. Zum Beispiel:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 Entsprechend können Sie bestimmte Member als nicht instanziiert und extern kennzeichnen:  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Sie können das Schlüsselwort `extern` verwenden, um den Compiler daran zu hindern, den gleichen Instanziierungscode in mehr als einem Objektmodul zu generieren. Sie müssen die Vorlagenfunktion instanziieren, indem Sie die angegebenen expliziten Vorlagenparameter in mindestens einem verknüpften Modul verwenden, wenn die Funktion aufgerufen wird. Andernfalls erhalten Sie einen Linkerfehler, wenn das Programm erstellt wird.  
  
> [!NOTE]
>  Das Schlüsselwort `extern` in der Spezialisierung gilt nur für Memberfunktionen, die außerhalb des Texts der Klasse definiert wurden. Die Funktionen, die in der Klassendeklaration definiert werden, gelten als Inlinefunktionen und werden immer instanziiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)