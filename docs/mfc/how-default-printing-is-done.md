---
title: Wie Standarddrucks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- default printing
- printing [MFC], default
- defaults, printing
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d2cf5b4a9bda3506a9558d5b723020dfe6d43396
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358914"
---
# <a name="how-default-printing-is-done"></a>Funktionsweise des Standarddrucks
Dieser Artikel beschreibt die Standard-Druckvorgang in Windows in Bezug auf die MFC-Framework.  
  
 In MFC-Anwendungen, die View-Klasse verfügt über eine Memberfunktion mit dem Namen `OnDraw` , der den Zeichencode enthält. `OnDraw` verwendet einen Zeiger auf eine [CDC](../mfc/reference/cdc-class.md) -Objekt als Parameter. Dass `CDC` Objekt repräsentiert den Gerätekontext, erhalten Sie das Image von erzeugten `OnDraw`. Wenn das Fenster, das Dokument anzeigen empfängt eine [WM_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213) Nachricht, der das Framework ruft `OnDraw` und übergibt sie zu einen Gerätekontext für den Bildschirm (eine [CPaintDC](../mfc/reference/cpaintdc-class.md) Objekt, das spezifisch sein). Dementsprechend `OnDraw`geht die Ausgabe auf dem Bildschirm.  
  
 Bei der Programmierung für Windows ist sendenden Ausgabe an den Drucker senden der Ausgabe auf dem Bildschirm sehr ähnlich. Dies ist, da die Windows Graphics Device Interface (GDI) hardwareunabhängiger ist. Sie können dieselben GDI-Funktionen für die Bildschirmanzeige oder für den Druck einfach mithilfe der entsprechenden Gerätekontext verwenden. Wenn die `CDC` Objekt, mit `OnDraw` empfängt stellt den Drucker `OnDraw`geht die Ausgabe an den Drucker.  
  
 Hier wird erläutert, wie MFC-Anwendungen einfacher drucken ausführen können, ohne dass zusätzlichen Aufwand ihrerseits. Das Framework übernimmt Anzeigen des Dialogfelds drucken, und erstellen einen Gerätekontext für den Drucker. Wenn der Benutzer des Befehls Drucken über das Menü Datei auswählt, übergibt die Ansicht dieser Gerätekontext, `OnDraw`, die das Dokument auf den Drucker gezeichnet.  
  
 Es gibt jedoch einige wichtige Unterschiede zwischen Bildschirm- und drucken. Beim Drucken, müssen Sie das Dokument in unterschiedliche Seiten und anzeigen, die sie einzeln nacheinander, anstelle der Anzeige von beliebigen Teil ist sichtbar in einem Fenster zu unterteilen. Daneben haben Sie Bedenken Sie das Papierformat (ob es Letter-Format, rechtliche Größen- oder einen Umschlag handelt). Möglicherweise möchten die verschiedenen Ausrichtungen, wie Quer- oder Hochformat gedruckt. Die Microsoft Foundation Class-Bibliothek kann nicht vorhersagen, wie Ihre Anwendung diese Probleme verarbeiten soll, damit es ein Protokoll zum Hinzufügen von Funktionen bietet.  
  
 Dass das Protokoll in diesem Artikel beschriebene [mehrseitige Dokumente](../mfc/multipage-documents.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Drucken](../mfc/printing.md)

