---
title: Verschieben des Speicherorts der Definition | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: c6d507ac-c61e-4da2-95c8-d504b42e2520
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44211105429e33c136999a7877ac6ee42af29f17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33327839"
---
# <a name="move-definition-location"></a>Definitionsspeicherort verschieben
**Zweck:** Sofortiges Verschieben einer Funktionsdefinition zu der entsprechenden Headerdatei.

**Anwendung:** Wenn Sie über eine Funktion verfügen, die in eine Headerdatei verschoben werden soll.  

**Grund:** Sie könnten des Feature manuell verschieben, jedoch verschiebt dieses Feature sie automatisch und erstellt bei Bedarf die Headerdatei.

**Vorgehensweise**:

1. Platzieren Sie Ihren Text oder Mauszeiger auf der Funktion, deren Definition Sie verschieben möchten.

   ![Markierter Code](images/movedefinition_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und klicken Sie im Kontextmenü auf **Definitionsspeicherort verschieben**.
   * **Maus**
     * Führen Sie einen Rechtsklick aus, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie anschließend im Kontextmenü auf **Definitionsspeicherort verschieben**.

1. Die Funktion wird in die entsprechende Headerdatei verschoben. Dies wird Ihnen in einem Vorschaufenster angezeigt.  Wenn die Headerdatei nicht vorhanden ist, wird diese erstellt und im Projekt platziert.

   ![Ergebnis des Erstellens der Deklaration/Definition](images/movedefinition_result.png)
