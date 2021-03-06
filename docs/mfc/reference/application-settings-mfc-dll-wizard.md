---
title: Anwendungseinstellungen, MFC-DLL-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: f021f2023af839413306c1e3d56dc741749cf216
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152045"
---
# <a name="application-settings-mfc-dll-wizard"></a>Anwendungseinstellungen, MFC-DLL-Assistent

Mithilfe dieser Seite des Assistenten für MFC-DLL entwerfen und zu grundlegende Funktionen zu einem neuen MFC-DLL-Projekt hinzufügen.

## <a name="dll-type"></a>DLL-Typ

Wählen Sie den Typ der DLL, die Sie erstellen möchten.

- **Reguläre MFC-DLL mithilfe von freigegebenen MFC-DLL**

   Wählen Sie diese Option, um die MFC-Bibliothek mit Ihrem Programm als einer gemeinsam genutzten DLL verknüpfen. Mit dieser Option können nicht Sie MFC-Objekte von der DLL und die aufrufende Anwendung freigeben. Das Programm führt Aufrufe an die MFC-Bibliothek zur Laufzeit. Diese Option verringert die Datenträger- und speicheranforderungen des Programms, wenn es von mehreren ausführbaren Dateien besteht, die die MFC-Bibliothek verwenden. Win32- und MFC-Programmen können Funktionen in der DLL aufrufen. Sie müssen die MFC-DLL mit dieser Art von Projekt verteilen.

- **Reguläre MFC-DLL mit MFC verknüpft statisch**

   Wählen Sie diese Option aus, um Ihr Programm statisch mit MFC-Bibliothek zum Zeitpunkt der Erstellung zu verknüpfen. Win32- und MFC-Programmen können Funktionen in der DLL aufrufen. Während Sie diese Option die Größe des Programms erhöht wird, müssen Sie nicht die MFC-DLL mit dieser Art von Projekt zu verteilen. Sie können keine MFC-Objekte von der DLL und die aufrufende Anwendung freigeben.

- **MFC-Erweiterungs-DLL**

   Wählen Sie diese Option, wenn Sie Ihre Anwendung die MFC-Bibliothek zur Laufzeit aufrufen möchten, und wenn Sie MFC-Objekten, von der DLL und die aufrufende Anwendung freigeben möchten. Diese Option verringert die Datenträger- und speicheranforderungen des Programms, wenn es von mehreren ausführbaren Dateien zusammengesetzt ist, dass alle MFC-Bibliothek verwenden. Nur MFC-Programmen können Funktionen in der DLL aufrufen. Sie müssen die MFC-DLL mit dieser Art von Projekt verteilen.

## <a name="additional-features"></a>Zusätzliche Funktionen

Wählen Sie, ob Ihre MFC-DLL die Automatisierung unterstützen soll, und, ob sie Windows-Sockets unterstützen soll.

- **Automatisierung**

   Wählen Sie **Automation** können Ihr Programm in einer anderen Anwendung implementierten Objekte zu bearbeiten. Auswählen von **Automation** auch Ihr Programm anderen Automatisierungsclients zur Verfügung gestellt. Finden Sie unter [Automation](../../mfc/automation.md) für Weitere Informationen.

- **Windows-sockets**

   Wählen Sie diese Option, um anzugeben, dass das Programm Windows-Sockets unterstützt. Windows-Sockets können Sie zum Schreiben von Programmen, die über TCP/IP-Netzwerke kommunizieren.

   Wenn die MFC-DLL mit Windows sockets-Unterstützung erstellt wurde, [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) initialisiert-Unterstützung für Sockets und die MFC-Header-Datei "stdafx.h" enthält die Datei AfxSock.h.

## <a name="see-also"></a>Siehe auch

[MFC-DLL-Assistent](../../mfc/reference/mfc-dll-wizard.md)<br/>
[Erstellen eines MFC-DLL-Projekts](../../mfc/reference/creating-an-mfc-dll-project.md)
