---
title: Message-Handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be4ccf9ec33e5ddf497193c1942e9f300f8cae57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347629"
---
# <a name="message-handlers"></a>Meldungshandler
In MFC, eine dedizierte *Handler* Funktion verarbeitet jede separate Nachricht. Meldungshandlerfunktionen sind Memberfunktionen einer Klasse. In dieser Dokumentation werden die Begriffe verwendet *Nachrichtenhandler Memberfunktion*, *Meldungshandlerfunktion*, *Nachrichtenhandler*, und *Handler*austauschbar. Einige Arten von Meldungshandler werden auch als "Befehlshandler" bezeichnet.  
  
 Schreiben Nachricht Handler Konten ein Großteil der Arbeit in einem Framework-Anwendung schreiben. Diese Artikelreihe wird beschrieben, wie der Nachrichtenverarbeitung Mechanismus funktioniert.  
  
 Leistungsumfang den Handler für eine Nachricht dafür ist, was Sie als Antwort auf diese Nachricht geschehen soll. Sie können die Handler erstellen, indem Sie das Fenster "Eigenschaften" der Klasse, und füllen Sie dann auf die mit dem Quellcode-Editors Handlercode.  
  
 Sie können alle Funktionen von Microsoft Visual C++ und MFC verwenden, die Handler zu schreiben. Eine Liste aller Klassen, finden Sie unter [Class Library Overview](../mfc/class-library-overview.md) in der *MFC-Referenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

