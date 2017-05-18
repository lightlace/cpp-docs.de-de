---
title: Anwendungseinstellungen, MFC-DLL-Assistent | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: df1e3de3e1548fe4c4c340a30127d9916998ba64
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="application-settings-mfc-dll-wizard"></a>Anwendungseinstellungen, MFC-DLL-Assistent
Mithilfe dieser Seite des MFC-DLL-Assistenten entwerfen und grundlegenden Funktionen zu einem neuen MFC-DLL-Projekt hinzugefügt.  
  
## <a name="dll-type"></a>DLL-Typ  
 Wählen Sie den Typ der DLL, die Sie erstellen möchten.  
  
 **Reguläre DLL, die mit gemeinsam genutzten MFC-DLL**  
 Wählen Sie diese Option, um die MFC-Bibliothek mit Ihrem Programm als gemeinsam genutzte DLL verknüpfen. Mit dieser Option können nicht Sie MFC-Objekte von der DLL und der aufrufenden Anwendung freigeben. Das Programm führt Aufrufe an die MFC-Bibliothek zur Laufzeit. Diese Option verringert die Datenträger- und Anforderungen für Ihr Programm aus mehreren ausführbaren Dateien zusammengesetzt ist, die die MFC-Bibliothek verwenden. Win32- und MFC-Programme können Funktionen in der DLL aufrufen. Sie müssen die MFC-DLL mit diesem Projekt verteilen.  
  
 **Reguläre DLL mit MFC statisch verknüpft ist**  
 Wählen Sie diese Option, um das Programm auf der MFC-Bibliothek zur Buildzeit statisch verknüpft. Win32- und MFC-Programme können Funktionen in der DLL aufrufen. Obwohl diese Option die Größe des Programms erhöht, müssen Sie nicht mit diesem Projekt die MFC-DLL weiterverteilen. MFC-Objekten kann nicht von der DLL und der aufrufenden Anwendung freigegeben werden.  
  
 **Erweiterung der MFC-DLL**  
 Wählen Sie diese Option, wenn das Programm auf der MFC-Bibliothek zur Laufzeit aufrufen soll, und wenn MFC-Objekte von der DLL und der aufrufenden Anwendung gemeinsam genutzt werden sollen. Diese Option verringert die Datenträger- und Anforderungen des Programms, wenn er aus mehreren ausführbaren Dateien zusammengesetzt ist, dass alle auf die MFC-Bibliothek verwenden. MFC-Programme können Funktionen in der DLL aufrufen. Sie müssen die MFC-DLL mit diesem Projekt verteilen.  
  
## <a name="additional-features"></a>Zusätzliche Funktionen  
 Wählen Sie fest, ob die MFC-DLL die Automatisierung und, ob die Windows-Sockets unterstützen soll.  
  
 **Automatisierung**  
 Wählen Sie **Automatisierung** an dem Programm die Bearbeitung in einem anderen Programm implementierten Objekte zu ermöglichen. Auswählen von **Automatisierung** auch Ihr Programm anderen Automatisierungsclients zur Verfügung gestellt. Finden Sie unter [Automatisierung](../../mfc/automation.md) Weitere Informationen.  
  
 **Windows-sockets**  
 Wählen Sie diese Option, um anzugeben, dass das Programm Windows-Sockets unterstützt. Windows-Sockets ermöglichen es Ihnen, Programme zu schreiben, die über TCP/IP-Netzwerke kommunizieren.  
  
 Wenn die MFC-DLL mit Windows sockets-Unterstützung erstellt wurde, [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) initialisiert die Unterstützung für Sockets und die MFC-Headerdatei StdAfx.h enthält die Datei AfxSock.h.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-DLL-Assistenten](../../mfc/reference/mfc-dll-wizard.md)   
 [Erstellen eines MFC-DLL-Projekts](../../mfc/reference/creating-an-mfc-dll-project.md)


