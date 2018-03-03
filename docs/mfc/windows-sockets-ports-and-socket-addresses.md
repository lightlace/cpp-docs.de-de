---
title: 'Windows Sockets: Ports und Socketadressen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c7b2e15761815b75ba8001ad4eb5a5c276f5056
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Sockets: Ports und Socketadressen
Dieser Artikel beschreibt die Begriffe "Port" und "Address" als mit Windows-Sockets verwendet.  
  
##  <a name="_core_port"></a>Port  
 Ein Port identifiziert einen eindeutigen Prozess für den ein Dienst bereitgestellt werden kann. Im Kontext vorhanden ist eine Anwendung, die Windows-Sockets unterstützt zugeordnet ein Port. Die Idee ist jede Windows-Sockets-Anwendung eindeutig zu identifizieren, damit Sie mehr als eine Windows Sockets-Anwendung, die gleichzeitig auf einem Computer ausgeführt haben, können.  
  
 Bestimmte Ports sind für gemeinsame Dienste, z. B. FTP reserviert. Vermeiden Sie die Verwendung dieser Ports, wenn Sie diese Art des Diensts bereitstellen. Windows Sockets-Spezifikation sind diese reservierte Ports. Die WINSOCK-Datei. H ebenfalls aufgelistet.  
  
 Damit die Windows-Sockets-DLL einen verwendbaren Port für die Sie auswählen können, übergeben Sie 0 als Wert für den Port ein. MFC wählt einen Portwert, der größer als 1.024 decimal. Sie können die Portwert, der durch Aufrufen von MFC ausgewählten Abrufen der [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) Memberfunktion.  
  
##  <a name="_core_socket_address"></a>Socketadresse  
 Jedes Socketobjekt, das eine Internetprotokoll (IP)-Adresse im Netzwerk zugeordnet ist. In der Regel ist die Adresse, einen Computernamen ein, z. B. "ftp.microsoft.com", oder einer gepunkteten Ziffer, z. B. "128.56.22.8".  
  
 Wenn Sie versuchen, ein Socket erstellen, in der Regel müssen nicht Sie eine eigene Adresse angeben.  
  
> [!NOTE]
>  Es ist möglich, dass Ihr Computer verfügt über mehrere Netzwerkkarten (oder Ihre Anwendung möglicherweise in einem solchen Computer eines Tages ausgeführt), jeweils ein anderes Netzwerk darstellen. Wenn dies der Fall ist, müssen Sie eine Adresse an die Netzwerkkarte, die Socket verwendet werden soll. Dies ist sicher, dass eine Verwendung erweiterter und kann Portabilitätsprobleme sein.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

