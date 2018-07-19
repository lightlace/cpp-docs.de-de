---
title: Konvertieren in ein Rohzeichenfolgenliteral | Microsoft-Dokumentation
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
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33328408"
---
# <a name="convert-to-raw-string-literal"></a>Zu Rohzeichenfolgenliteral konvertieren
**Zweck:** Umwandeln einer beliebigen Zeichenfolge in ein C++-Rohzeichenfolgenliteral.

**Anwendung:** Wenn Sie über eine Zeichenfolge mit Escapezeichen verfügen, die nicht als Escapezeichen verarbeitet werden sollen.

**Grund:** Sie könnten doppelte Escapezeichen verwenden, dies führt jedoch in den meisten Fällen zu verwirrenden und schwer lesbaren Zeichenfolgen.  Mithilfe von Rohzeichenfolgenliteralen sind Zeichenfolgen viel einfacher zu lesen.

**Vorgehensweise**:

1. Platzieren Sie Ihren Text oder Mauszeiger auf der Escapezeichenfolge, die konvertiert werden soll.

   ![Markierter Code](images/stringliteral_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und klicken Sie im Kontextmenü auf **Zu Rohzeichenfolgenliteral konvertieren**.
   * **Maus**
     * Klicken Sie mit der rechten Maustaste auf den Code, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie anschließend im Kontextmenü auf **Zu Rohzeichenfolgenliteral konvertieren**.
     * Klicken Sie auf das ![Glühbirnensymbol](images/bulb.png), das am linken Rand angezeigt wird, und klicken Sie im Kontextmenü auf **Zu Rohzeichenfolgenliteral konvertieren**.

1. Die Zeichen folge wird sofort in ein Rohzeichenfolgenliteral konvertiert.  

   ![Rohzeichenfolgenliteral-Ergebnis](images/stringliteral_result.png)