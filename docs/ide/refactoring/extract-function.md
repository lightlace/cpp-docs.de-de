---
title: Extract-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/16/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: e31d1249-9705-4511-acbd-9f6fe73bdf2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fc4d48c972bca9352f326085574e4cf4df83aea
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33333156"
---
# <a name="extract-function"></a>Extract-Funktion
**Zweck:** Umwandeln eines Codefragments in dessen eigene Funktion.

**Anwendung:** Wenn Sie über ein Fragment von vorhandenem Code in einer Funktion verfügen, das von einer anderen Funktion aufgerufen werden muss.  

**Vorteile**: Sie könnten diesen Code kopieren und einfügen, dies würde jedoch zu einer Duplizierung führen.  Eine bessere Lösung besteht darin, dieses Fragment in eine eigene Funktion umzugestalten, die von anderen Funktion beliebig aufgerufen werden kann.

**Vorgehensweise**:

1. Markieren Sie den zu extrahierenden Code:

   ![Markierter Code](images/extractfunction_highlight.png)

1. Führen Sie dann eine der folgenden Aktionen aus:
   * **Tastatur**
     * Drücken Sie **STRG+R** und dann **STRG+M**.  (Beachten Sie, dass Ihre Tastenkombination je nach dem gewählten Profil möglicherweise abweicht.)
     * Drücken Sie **STRG+.**, um das Menü **Schnellaktionen und Refactorings** aufzurufen, und klicken Sie im Kontextmenü auf **Funktion extrahieren (experimentell)**.
   * **Maus**
     * Klicken Sie auf **Bearbeiten > Umgestalten > Funktion extrahieren (experimentell)**.
     * Klicken Sie mit der rechten Maustaste auf den Code, und klicken Sie auf das Menü **Schnellaktionen und Refactorings**. Klicken Sie dann im Kontextmenü auf **Funktion extrahieren (experimentell)**.
     * Klicken Sie auf das ![Glühbirnensymbol](images/bulb.png), das am linken Rand angezeigt wird, und klicken Sie im Kontextmenü auf **Funktion extrahieren (experimentell)**.

1. Geben Sie im Fenster **Funktion/Methode extrahieren (experimentell)** den neuen Funktionsnamen ein, wählen Sie aus, wo der Code platziert werden soll, und klicken Sie auf **OK**.  

   ![Funktion „Funktion extrahieren“](images/extractfunction_dialog.png)

1. Die neue Funktion wird am angegebenen Ort erstellt, ein Funktionsprototyp wird in der entsprechenden Headerdatei erstellt und der ursprüngliche Code wird so geändert, dass er die Funktion aufruft.

   ![Ergebnis der Extract-Funktion](images/extractfunction_result.png)