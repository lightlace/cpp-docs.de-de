---
title: Windows Sockets-Klassen
ms.date: 11/04/2016
f1_keywords:
- vc.classes.net
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 18537c0de09185c8cd219e3d17ef8bb297e1d711
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433604"
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

