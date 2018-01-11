---
title: Implementierung von reinen | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea9b4719-34a3-474a-b4ec-05b1859f80f1
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f311c2e5832754bfd785084b9aa930b5dbe43845
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="implement-pure-virtuals"></a>Implementierung von reinen
**Was:** können Sie den Code erforderlich, um alle reinen virtuellen Methoden in einer Klasse implementieren sofort zu generieren. 

**Wann:** erben von einer Klasse mit reinen virtuellen Funktionen werden sollen.  

**Grund:** konnte Sie alle reine virtuelle Funktionen nacheinander, manuell implementieren, aber diese Funktion automatisch alle Methodensignaturen generiert.

**Vorgehensweise:**

1. Platzieren Sie den Text oder mit dem Mauszeiger-Cursor über die Klasse, in der Sie die reinen virtuellen Funktionen der Basisklasse implementieren möchten.

   ![Hervorgehobene code](images/virtuals_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü  **implementieren alle rein virtuellen Aufrufe für die Klasse*ClassName*"** im Kontextmenü der, in dem  *Klassenname* ist der Name der ausgewählten Klasse.
   * **Maus**
     * Mit der rechten Maustaste, und wählen Sie die **Schnellaktionen und Refactorings** Menü  **implementieren alle rein virtuellen Aufrufe für die Klasse*ClassName*"** aus dem Kontextmenü, in dem  *Klassenname* ist der Name der ausgewählten Klasse.

1. Die rein virtuelle Methodensignaturen werden automatisch erstellt, implementiert werden.

   ![Implementieren von reinen Ergebnis](images/virtuals_result.png)
