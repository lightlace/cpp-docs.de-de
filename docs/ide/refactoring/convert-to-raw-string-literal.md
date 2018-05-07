---
title: Konvertieren in unformatiertes Zeichenfolgenliteral | Microsoft Docs
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b98825719e7b3c0d8eb760a2ec50644b5eddd54e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="convert-to-raw-string-literal"></a>Zu Rohzeichenfolgenliteral konvertieren
**Was:** können Sie eine beliebige Zeichenfolge in eine C++-rohzeichenfolge literal zu aktivieren.

**Wann:** stehen Ihnen eine Zeichenfolge mit Escapezeichen darf nicht als Escapezeichen verarbeitet werden.

**Grund:** könnten Sie Double-Escape-Zeichen, aber diesem häufig führt zu einem verwirrend und kann nicht gelesen Zeichenfolgen.  Unformatierte Zeichenfolgenliterale mit kann Zeichenfolgen viel einfacher zu lesen.

**Vorgehensweise**:

1. Platzieren Sie Text oder Mauscursor über die mit Escapezeichen versehene Zeichenfolge zu konvertieren.

   ![Markierter Code](images/stringliteral_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, Trigger die **Schnellaktionen und Refactorings** Menü **rohzeichenfolgenliteral konvertieren** aus dem Kontextmenü.
   * **Maus**
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **rohzeichenfolgenliteral konvertieren** aus dem Kontextmenü.
     * Klicken Sie auf die ![Lightbulb](images/bulb.png) im linken Rand, und wählen erscheint das Symbol für **rohzeichenfolgenliteral konvertieren** aus dem Kontextmenü.

1. Die Zeichenfolge wird sofort in ein unformatiertes Zeichenfolgenliteral konvertiert werden.  

   ![RAW-Zeichenfolgenliteralen Ergebnis](images/stringliteral_result.png)