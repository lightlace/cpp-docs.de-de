---
title: Verwalten der Statusdaten von MFC-Modulen
ms.date: 11/04/2016
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
ms.openlocfilehash: 757fe9d8b4c9985cd3fa36d399cdc92057c03011
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562213"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>Verwalten der Statusdaten von MFC-Modulen

Dieser Artikel beschreibt die Statusdaten von MFC-Modulen und wie dieser Status aktualisiert wird, wenn es sich bei der Ablauf der Ausführung (im Path-Code wird sich durch eine Anwendung, wenn die Ausführung) gibt, und bewirkt, dass ein Modul. Modulzustände mit den Makros AFX_MANAGE_STATE und METHOD_PROLOGUE wechseln, wird ebenfalls erläutert.

> [!NOTE]
>  Das Begriff "Modul" Hier bezieht sich ein ausführbares Programm oder eine DLL (oder einen Satz von DLLs) an, die unabhängig vom Rest der Anwendung ausgeführt werden, verwendet jedoch eine gemeinsame Kopie der MFC-DLL. Ein ActiveX-Steuerelement ist ein typisches Beispiel für ein Modul.

Wie in der folgenden Abbildung gezeigt wird, hat MFC Statusdaten für jedes Modul in einer Anwendung verwendet. Beispiele für diese Daten sind, wird der Windows-Instanz (für das Laden von Ressourcen verwendet), Zeiger auf die aktuelle `CWinApp` und `CWinThread` Objekte von einer Anwendung, einen Zähler für OLE-Modul und eine Vielzahl von Zuordnungen, die die Verbindungen zwischen verwalten Windows Objekt behandelt und die entsprechenden Instanzen von MFC-Objekten. Wenn eine Anwendung mehrere Module verwendet, die Daten der einzelnen Module ist jedoch nicht Anwendung breit. Stattdessen verfügt jedes Modul eine eigene Kopie der Daten für die MFC Zustand.

![Zustandsdaten eines einzelmoduls &#40;Anwendung&#41;](../mfc/media/vc387n1.gif "vc387n1") Zustandsdaten eines Einzelmoduls (Anwendung)

Zustandsdaten des Moduls in einer Struktur enthalten ist, und es ist immer verfügbar, über einen Zeiger auf dieser Struktur. Wenn der Ausführungsablauf von einem bestimmten Modul eingibt, wie in der folgenden Abbildung gezeigt, muss der Status dieses Moduls den Status "current" oder "effektive" sein. Daher muss jeder Thread-Objekt einen Zeiger auf den effektiven Statusstruktur der Anwendung. Halten diesen Zeiger, die stets Zeiten ist wichtig, Verwalten des globalen Status der Anwendung und die Wahrung der Integrität des Moduls Zustand. Eine fehlerhafte Verwaltung des globalen Status kann zu unvorhersehbarem Anwendungsverhalten führen.

![Zustandsdaten mehrerer Module](../mfc/media/vc387n2.gif "vc387n2") Statusdaten von mehreren Modulen

Das heißt, ist jedes Modul für ordnungsgemäß Wechseln zwischen Modulzustände alle den-Einstiegspunkten verantwortlich. Ein "Einstiegspunkt" ist eine beliebige Stelle, über der Ablauf der Ausführung des Moduls Code eingeben können. Einstiegspunkte sind:

- [Exportierte Funktionen in einer DLL](../mfc/exported-dll-function-entry-points.md)

- [Memberfunktionen von COM-Schnittstellen](../mfc/com-interface-entry-points.md)

- [Fensterprozeduren](../mfc/window-procedure-entry-points.md)

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

