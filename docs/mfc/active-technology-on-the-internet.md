---
title: Active Technology für das Internet | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet applications [MFC], Active technology
ms.assetid: 6f782aa1-5c2f-47a2-9e63-ddd0829d5a08
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30aef153dc99c0cbdc4de537496e42ab2bb0459f
ms.sourcegitcommit: a3c9e7888b8f437a170327c4c175733ad9eb0454
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50204508"
---
# <a name="active-technology-on-the-internet"></a>Active Technology für das Internet

Active Technology ist eine offene Plattform, mit dem Entwickler, die interessante, dynamische Inhalte und Anwendungen im globalen Internet oder ein Netzwerk des Unternehmens interne, bekannt als Intranet erstellen kann. Die wichtigen Technologien von Microsoft bereitgestellt werden, für die Internet-Programmierung werden nachfolgend beschrieben.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

## <a name="activex-controls"></a>ActiveX-Steuerelemente

ActiveX-Steuerelementen (früher OLE-Steuerelemente) sind Objekte, die in Webseiten oder eine andere Anwendung, die einem ActiveX-Steuerelement-Container eingefügt werden können. Beispiele sind die Schaltflächen, Börsenticker- und Chart-Steuerelementen. Weitere Informationen finden Sie unter [ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md).

## <a name="internet-data-download-services"></a>Internet Data herunterladen Services

Daten können über das Internet, die Verwendung gemeinsamer Protokolle heruntergeladen werden: HTTP, FTP und Gopher. Die MFC-WinInet-Klassen erleichtern die zum Übertragen von Daten mithilfe von HTTP, FTP und Gopher-Protokolle durch das abstrahieren die TCP/IP und WinSock-Protokolle. Die asynchrone Moniker-MFC-Klassen bieten eine Möglichkeit zum Herunterladen von Dateien ohne Blockierung und zum asynchronen Rendern großer Objekte. Weitere Informationen finden Sie unter [Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md).

## <a name="active-scripts"></a>Aktive Skripts

VBScript und andere Skriptsprachen verbinden Steuerelemente, und fügen interaktive Funktionen in Webseiten. Skripterstellung wechselt vom Server an den Client verarbeiten. Beispielsweise können von Formulareinträgen auf dem Client überprüft und dann an den Server gesendet werden.

## <a name="html-extensions"></a>HTML-Erweiterungen

HTML-Erweiterungen, z. B. das Object-Tag, wurden zur Unterstützung von Steuerelementen und Skripts hinzugefügt.

## <a name="see-also"></a>Siehe auch

[Grundlagen der MFC-Internetprogrammierung](../mfc/mfc-internet-programming-basics.md)<br/>
[ActiveX-Steuerelemente für das Internet](../mfc/activex-controls-on-the-internet.md)<br/>
[Win32-Interneterweiterungen (WinInet)](../mfc/win32-internet-extensions-wininet.md)

