---
title: Windows Sockets-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.net
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 4abdd8f8fbfc115b5014ffd0b3a37df357852b16
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371801"
---
# <a name="windows-sockets-classes"></a>Windows Sockets-Klassen

Windows Sockets bieten eine Möglichkeit des Netzwerk-Protokoll-unabhängigen für die Kommunikation zwischen zwei Computern. Diese Sockets können synchron sein (das Programm wartet, bis die Kommunikation erfolgt) oder asynchron (das Programm weiterhin ausgeführt, während die Kommunikation vor sich geht).

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
Kapselt die Windows Sockets-API in einen einfachen Wrapper.

[CSocket](../mfc/reference/csocket-class.md)<br/>
Abgeleitet von höheren Abstraktionsgrad `CAsyncSocket`. Es wird synchron ausgeführt.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Stellt eine `CFile` Schnittstelle, um einen Windows Socket.

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../mfc/class-library-overview.md)
