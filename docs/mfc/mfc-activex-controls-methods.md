---
title: 'MFC-ActiveX-Steuerelemente: Methoden'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
ms.openlocfilehash: 71c4cdd5ea07b3468b7878a221129a0de5eb4974
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386368"
---
# <a name="mfc-activex-controls-methods"></a>MFC-ActiveX-Steuerelemente: Methoden

Ein ActiveX-Steuerelement löst Ereignisse für die Kommunikation zwischen sich selbst und die Control-Container aus. Ein Container kann auch über Methoden und Eigenschaften mit einem Steuerelement kommunizieren. Methoden werden auch Funktionen aufgerufen werden.

Methoden und Eigenschaften bieten eine exportierte Schnittstelle für die Verwendung von anderen Anwendungen, z. B. Benutzeroberflächenautomatisierungs-Clients und ActiveX-Steuerelementcontainer. Weitere Informationen zu Eigenschaften von ActiveX-Steuerelements, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md).

Methoden ähneln sich und Zweck auf die Memberfunktionen einer C++-Klasse. Es gibt zwei Arten von Methoden, die das Steuerelement implementieren kann: vordefinierte und benutzerdefinierte. Für vordefinierte Ereignisse Kursdiagramme Methoden ähneln diese Methoden für die [COleControl](../mfc/reference/colecontrol-class.md) stellt eine Implementierung bereit. Weitere Informationen zu vordefinierten Methoden, finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md). Vom Entwickler definierte benutzerdefinierte Methoden ermöglichen die weitere Anpassung des Steuerelements. Weitere Informationen finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden](../mfc/mfc-activex-controls-adding-custom-methods.md).

Die Microsoft Foundation Class-Bibliothek (MFC) implementiert einen Mechanismus, der das Steuerelement, um vordefinierte und benutzerdefinierte Methoden unterstützen kann. Der erste Teil ist die Klasse `COleControl`. Abgeleitet von `CWnd`, `COleControl` Memberfunktionen Unterstützung von vordefinierten Methoden, die für alle ActiveX-Steuerelemente gelten. Im zweiten Teil dieser Mechanismus ist die Dispatchzuordnung. Eine Dispatchzuordnung ähnelt einer meldungszuordnung ist. anstatt die Zuordnung einer Funktion an eine Windows-Nachrichten-ID ist eine Dispatchzuordnung jedoch virtuellen Memberfunktionen IDispatch-IDS zugeordnet.

Für ein Steuerelement auf verschiedene Methoden ordnungsgemäß unterstützt muss ihre Klasse eine Dispatchzuordnung deklarieren. Dies erfolgt durch die folgende Codezeile befindet sich im Klasse Control-Header (. H)-Datei:

[!code-cpp[NVC_MFC_AxUI#13](../mfc/codesnippet/cpp/mfc-activex-controls-methods_1.h)]

Der Hauptzweck der Dispatchzuordnung ist die Beziehung zwischen den Methodennamen, die von einem externen Anrufer (z. B. Container) und die Memberfunktionen der Klasse des Steuerelements, die die Methoden implementieren verwendet herstellen. Nachdem die Dispatchzuordnung deklariert wurde, muss er in der Implementierung des Steuerelements definiert werden (. CPP)-Datei. Die folgenden Codezeilen definieren die Dispatchzuordnung:

[!code-cpp[NVC_MFC_AxUI#14](../mfc/codesnippet/cpp/mfc-activex-controls-methods_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#15](../mfc/codesnippet/cpp/mfc-activex-controls-methods_3.cpp)]

Bei Verwendung der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md) um das Projekt zu erstellen, diese Zeilen automatisch hinzugefügt. Wenn die MFC-ActiveX-Steuerelement-Assistent nicht verwendet wurde, müssen Sie diese Zeilen auch manuell hinzufügen.

In den folgenden Artikeln werden die Methoden ausführlich erörtert:

- [MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md)

- [MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden](../mfc/mfc-activex-controls-adding-custom-methods.md)

- [MFC-ActiveX-Steuerelemente: Zurückgeben von Fehlercodes aus einer Methode](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)
