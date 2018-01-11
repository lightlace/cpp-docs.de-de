---
title: Message-Handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d1b906a49d7da7ed8505252a1759d7ea00fcda1f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="message-handlers"></a>Meldungshandler
In MFC, eine dedizierte *Handler* Funktion verarbeitet jede separate Nachricht. Meldungshandlerfunktionen sind Memberfunktionen einer Klasse. In dieser Dokumentation werden die Begriffe verwendet *Nachrichtenhandler Memberfunktion*, *Meldungshandlerfunktion*, *Nachrichtenhandler*, und *Handler*austauschbar. Einige Arten von Meldungshandler werden auch als "Befehlshandler" bezeichnet.  
  
 Schreiben Nachricht Handler Konten ein Großteil der Arbeit in einem Framework-Anwendung schreiben. Diese Artikelreihe wird beschrieben, wie der Nachrichtenverarbeitung Mechanismus funktioniert.  
  
 Leistungsumfang den Handler für eine Nachricht dafür ist, was Sie als Antwort auf diese Nachricht geschehen soll. Sie können die Handler erstellen, indem Sie das Fenster "Eigenschaften" der Klasse, und füllen Sie dann auf die mit dem Quellcode-Editors Handlercode.  
  
 Sie können alle Funktionen von Microsoft Visual C++ und MFC verwenden, die Handler zu schreiben. Eine Liste aller Klassen, finden Sie unter [Class Library Overview](../mfc/class-library-overview.md) in der *MFC-Referenz*.  
  
## <a name="see-also"></a>Siehe auch  
 [Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

