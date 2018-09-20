---
title: Message-Handler | Microsoft-Dokumentation
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
ms.openlocfilehash: 22dde243bb6d8e8a283e670804d4b8b6cad9082c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406749"
---
# <a name="message-handlers"></a>Meldungshandler

In MFC, ein dediziertes *Handler* Funktion verarbeitet jede separate Nachricht. Meldungshandler-Funktionen werden die Memberfunktionen einer Klasse. In dieser Dokumentation werden die Begriffe verwendet *-Nachrichtenhandler-Memberfunktion*, *-Meldungshandler*, *Meldungshandler*, und *Handler*Synonym verwenden lassen. Einige Arten von Meldungshandler werden auch als "Befehlshandler." bezeichnet.

Das Message-Handler-Konten ein Großteil der Arbeit beim Schreiben einer Framework-Anwendung schreiben. In diesen Abschnitten wird beschrieben, wie der Mechanismus für die Verarbeitung von Nachrichten funktioniert.

Funktionsweise den Handler für eine Nachricht dafür ist, was als Reaktion auf diese Nachricht geschehen soll. Sie können die Handler erstellen, indem Sie das Fenster "Eigenschaften" der Klasse, und geben Sie dann in der Handler-Code, die mithilfe der Quellcode-Editor.

Sie können alle Funktionen von Microsoft Visual C++ und MFC verwenden, die Handler zu schreiben. Eine Liste aller Klassen, finden Sie unter [Übersicht über die Klassenbibliothek](../mfc/class-library-overview.md) in die *MFC-Referenz*.

## <a name="see-also"></a>Siehe auch

[Meldungen und Befehle im Framework](../mfc/messages-and-commands-in-the-framework.md)

