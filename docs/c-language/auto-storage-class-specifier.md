---
title: auto-Speicherklassenspezifizierer | Microsoft-Dokumentation
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
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
caps.latest.revision: 6
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
ms.openlocfilehash: a5c470eb63060b92e10ae3e31c2d6ccb6df22165
ms.contentlocale: de-de
ms.lasthandoff: 05/18/2017

---
# <a name="auto-storage-class-specifier"></a>auto-Speicherklassenspezifizierer
Der **auto**-Speicherklassenspezifizierer deklariert eine automatische Variable, eine Variable mit lokaler Lebensdauer. Eine **auto**-Variable ist nur im Block sichtbar, in dem sie deklariert ist. Deklarationen von **auto**-Variablen können Initialisierer enthalten, wie unter [Initialisierung](../c-language/initialization.md) erläutert. Da Variablen mit der **auto**-Speicherklasse nicht automatisch initialisiert werden, sollten Sie sie entweder bei ihrer Deklaration explizit initialisieren oder ihnen Anfangswerte in Anweisungen innerhalb des Blocks zuweisen. Die Werte von nicht initialisierten **auto**-Variablen sind nicht definiert. (Eine lokale Variable der **auto**- oder **register**-Speicherklasse wird jedes Mal initialisiert, wenn sie in den Bereich gelangt und ein Initialisierer angegeben ist.)  
  
 Eine interne **static**-Variable (eine statische Variable mit lokalem oder Blockbereich) kann mit der Adresse eines externen oder **static**-Elements, aber nicht mit der Adresse eines anderen **auto**-Elements initialisiert werden, da die Adresse eines **auto**-Elements keine Konstante ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../cpp/auto-keyword.md)
