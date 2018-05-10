---
title: auto-Speicherklassenspezifizierer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4054b723c1e44c94be9d112f6bfbd74db8f857ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="auto-storage-class-specifier"></a>auto-Speicherklassenspezifizierer
Der **auto**-Speicherklassenspezifizierer deklariert eine automatische Variable, eine Variable mit lokaler Lebensdauer. Eine **auto**-Variable ist nur im Block sichtbar, in dem sie deklariert ist. Deklarationen von **auto**-Variablen können Initialisierer enthalten, wie unter [Initialisierung](../c-language/initialization.md) erläutert. Da Variablen mit der **auto**-Speicherklasse nicht automatisch initialisiert werden, sollten Sie sie entweder bei ihrer Deklaration explizit initialisieren oder ihnen Anfangswerte in Anweisungen innerhalb des Blocks zuweisen. Die Werte von nicht initialisierten **auto**-Variablen sind nicht definiert. (Eine lokale Variable der **auto**- oder **register**-Speicherklasse wird jedes Mal initialisiert, wenn sie in den Bereich gelangt und ein Initialisierer angegeben ist.)  
  
 Eine interne **static**-Variable (eine statische Variable mit lokalem oder Blockbereich) kann mit der Adresse eines externen oder **static**-Elements, aber nicht mit der Adresse eines anderen **auto**-Elements initialisiert werden, da die Adresse eines **auto**-Elements keine Konstante ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Auto-Schlüsselwort](../cpp/auto-keyword.md)