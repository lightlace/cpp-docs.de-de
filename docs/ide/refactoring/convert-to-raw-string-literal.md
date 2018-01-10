---
title: Konvertieren in unformatiertes Zeichenfolgenliteral | Microsoft Docs
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fffbfee4-66ee-42ba-aeb9-df07fb702c51
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12aa512270ecce4564561634f99be9cbf155448a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="convert-to-raw-string-literal"></a>Zu Rohzeichenfolgenliteral konvertieren
**Was:** können Sie eine beliebige Zeichenfolge in eine C++-rohzeichenfolge literal zu aktivieren.

**Wann:** stehen Ihnen eine Zeichenfolge mit Escapezeichen darf nicht als Escapezeichen verarbeitet werden.

**Grund:** könnten Sie Double-Escape-Zeichen, aber diesem häufig führt zu einem verwirrend und kann nicht gelesen Zeichenfolgen.  Unformatierte Zeichenfolgenliterale mit kann Zeichenfolgen viel einfacher zu lesen.

**Vorgehensweise:**

1. Platzieren Sie Text oder Mauscursor über die mit Escapezeichen versehene Zeichenfolge zu konvertieren.

   ![Hervorgehobene code](images/stringliteral_highlight.png)

1. Als Nächstes führen Sie eine der folgenden:
   * **Tastatur**
     * Drücken Sie **STRG +.** Trigger die **Schnellaktionen und Refactorings** Menü **rohzeichenfolgenliteral konvertieren** aus dem Kontextmenü.
   * **Maus**
     * Mit der rechten Maustaste in des Codes, wählen Sie die **Schnellaktionen und Refactorings** Menü **rohzeichenfolgenliteral konvertieren** aus dem Kontextmenü.
     * Klicken Sie auf die ![Lightbulb](images/bulb.png) im linken Rand, und wählen erscheint das Symbol für **rohzeichenfolgenliteral konvertieren** aus dem Kontextmenü.

1. Die Zeichenfolge wird sofort in ein unformatiertes Zeichenfolgenliteral konvertiert werden.  

   ![RAW-Zeichenfolgenliteralen Ergebnis](images/stringliteral_result.png)