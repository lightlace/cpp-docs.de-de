---
title: Anwendungseinstellungen, MFC-DLL-Assistent | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1a243b790881452a983c43fb92d8ebea18c26bcc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="application-settings-mfc-dll-wizard"></a>Anwendungseinstellungen, MFC-DLL-Assistent
Verwenden Sie diese Seite des MFC-DLL-Assistenten entworfen und grundlegende Funktionen zu einem neuen MFC-DLL-Projekt hinzufügen.  
  
## <a name="dll-type"></a>DLL-Typ  
 Wählen Sie den Typ der DLL, die Sie erstellen möchten.  
  
 **Reguläre MFC-DLL mithilfe von freigegebenen MFC-DLL**  
 Wählen Sie diese Option, um die MFC-Bibliothek mit Ihrem Programm als eine freigegebene DLL verknüpfen. Bei Verwendung dieser Option können nicht Sie MFC-Objekte zwischen der DLL und die aufrufende Anwendung freigeben. Das Programm führt Aufrufe an die MFC-Bibliothek zur Laufzeit. Diese Option verringert die Festplatten- und Anforderungen des Programms an, wenn es aus mehreren ausführbaren Dateien besteht, die die MFC-Bibliothek verwenden. Win32- und MFC-Programme können Funktionen in der DLL aufrufen. Sie müssen die MFC-DLL mit diesen Typ von Projekt erneut verteilen.  
  
 **Reguläre MFC-DLL mit MFC verknüpft statisch**  
 Wählen Sie diese Option, um das Programm statisch mit MFC-Bibliothek während des Buildvorgangs verknüpfen. Win32- und MFC-Programme können Funktionen in der DLL aufrufen. Während dieser Option die Größe des Programms erhöht wird, müssen Sie nicht die MFC-DLL mit diesen Typ von Projekt zu verteilen. MFC-Objekte können nicht zwischen der DLL und die aufrufende Anwendung freigegeben werden.  
  
 **MFC-Erweiterungs-DLL**  
 Wählen Sie diese Option, wenn Sie das Programm zur Laufzeit auf die MFC-Bibliothek aufrufen möchten, und wenn Sie MFC-Objekte zwischen der DLL und die aufrufende Anwendung freigeben möchten. Diese Option verringert die Festplatten- und Anforderungen des Programms an, wenn sie mehrere ausführbare Dateien besteht, von denen die MFC-Bibliothek verwendet. MFC-Programmen können Funktionen in der DLL aufrufen. Sie müssen die MFC-DLL mit diesen Typ von Projekt erneut verteilen.  
  
## <a name="additional-features"></a>Zusätzliche Funktionen  
 Wählen Sie fest, ob die MFC-DLL die Automatisierung und, ob sie Windows-Sockets unterstützen soll.  
  
 **Automatisierung**  
 Wählen Sie **Automatisierung** an dem Programm die Bearbeitung in einer anderen Anwendung implementierten Objekte zu ermöglichen. Auswählen von **Automatisierung** auch Ihr Programm anderen Automatisierungsclients zur Verfügung gestellt. Finden Sie unter [Automatisierung](../../mfc/automation.md) für Weitere Informationen.  
  
 **Windows-sockets**  
 Wählen Sie diese Option, um anzugeben, dass das Programm Windows-Sockets unterstützt. Windows-Sockets ermöglichen es Ihnen, Programme zu schreiben, die über TCP/IP-Netzwerke kommunizieren.  
  
 Wenn die MFC-DLL mit Windows-sockets unterstützen erstellt, [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) initialisiert für Sockets unterstützen und die MFC-Header-Datei "stdafx.h" enthält die Datei AfxSock.h.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-DLL-Assistent](../../mfc/reference/mfc-dll-wizard.md)   
 [Erstellen eines MFC-DLL-Projekts](../../mfc/reference/creating-an-mfc-dll-project.md)

