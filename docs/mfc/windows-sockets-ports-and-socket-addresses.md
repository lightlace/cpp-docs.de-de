---
title: 'Windows Sockets: Ports und Socketadressen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f97bfa42e379f0806eb85e3f030465b2a181d01
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379663"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Sockets: Ports und Socketadressen

Dieser Artikel erläutert die Begriffe "Port" und "Address" als mit Windows Sockets verwendet.

##  <a name="_core_port"></a> Port

Ein Port identifiziert einen eindeutigen Prozess für den ein Dienst bereitgestellt werden kann. Im vorliegenden Kontext ist eine Anwendung, die Windows-Sockets unterstützt zugeordnet. Die Idee besteht darin, jede Windows Sockets-Anwendung eindeutig zu identifizieren, müssen Sie mehrere Windows Sockets-Anwendungen, die auf einem Computer ausgeführt wird, zur gleichen Zeit können.

Bestimmte Ports sind für gemeinsame Dienste, z. B. FTP reserviert. Vermeiden Sie, ob Sie diese Ports verwenden, es sei denn, Sie diese Art des Diensts bereitstellen. Diese reservierte Ports wird erläutert, die Windows Sockets-Spezifikation. Die WINSOCK-Datei. H ebenfalls aufgelistet.

Damit können die Windows Sockets-DLL, die einen verwendbaren Port auswählen, übergeben Sie 0 als Wert für den Port ein. MFC wählt einen Portwert, der größer als 1.024 decimal. Sie können die Portwert, der durch Aufrufen von MFC ausgewählten Abrufen der [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) Member-Funktion.

##  <a name="_core_socket_address"></a> Socketadresse

Jedes Socketobjekt, das eine IP (Internet Protocol)-Adresse im Netzwerk zugeordnet ist. In der Regel ist die Adresse, einen Computernamen ein, z. B. "ftp.microsoft.com", oder eine gepunktete an, z. B. "128.56.22.8".

Wenn Sie sich bemühen, einen Socket zu erstellen, in der Regel müssen nicht Sie Ihre eigene Adresse angeben.

> [!NOTE]
>  Es ist möglich, dass Ihr Computer verfügt über mehrere Netzwerkkarten (oder die Anwendung könnte eines Tages auf einen solchen Computer ausgeführt), jeweils ein anderes Netzwerk darstellen. Wenn dies der Fall ist, müssen Sie eine Adresse an der Netzwerkkarte, die Socket verwendet werden soll. Dies ist sicher, dass eine erweiterte nutzungs- und kann Portabilitätsprobleme sein.

Weitere Informationen finden Sie unter:

- [Windows-Sockets: Verwenden der Klasse CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows-Sockets: Verwenden von Sockets mit Archiven](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows-Sockets: Wie Sockets mit Archiven arbeiten](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows-Sockets: Blockieren](../mfc/windows-sockets-stream-sockets.md)

- [Windows-Sockets: Datagrammsockets](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Siehe auch

[Windows-Sockets in MFC](../mfc/windows-sockets-in-mfc.md)

