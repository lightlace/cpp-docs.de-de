---
title: SDI und MDI
ms.date: 11/04/2016
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
ms.openlocfilehash: 725249e5a71e8ee097c641e5972e3cc8bb0e3e33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62308529"
---
# <a name="sdi-and-mdi"></a>SDI und MDI

MFC erleichtert die Arbeit mit sowohl Single Document Interface (SDI) und Multiple Document Interface (MDI)-Anwendungen.

SDI-Anwendungen können nur ein Fenster des geöffneten Dokuments Frame zu einem Zeitpunkt. MDI-Anwendungen können mehrere Dokument-Frame-Fensters in der gleichen Instanz von einer Anwendung geöffnet sein. MDI-Anwendung verfügt über ein Fenster, in der mehrere MDI untergeordnete Fenster, die selbst Rahmenfenster sind, geöffnet werden können, jeweils ein separates Dokument. In einigen Anwendungen können die untergeordneten Fenster verschiedener Typen, z. B. Chart-Windows und Windows der Tabelle sein. In diesem Fall kann die Menüleiste ändern, da untergeordnete MDI-Fenster mit unterschiedlichen Typen aktiviert werden.

> [!NOTE]
>  Unter Windows 95 und höher, sind Anwendungen häufig SDI, da das Betriebssystem eine Ansicht "dokumentbasierter" übernommen hat.

Weitere Informationen finden Sie unter [Dokumente, Ansichten und das Framework](../mfc/documents-views-and-the-framework.md).

## <a name="see-also"></a>Siehe auch

[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
