---
title: Vor- und Nachteile der Methode, um eine Verknüpfung zu der CRT
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_MIN_CRT macro
ms.assetid: 49b485f7-9487-49e4-b12a-0f710b620e2b
ms.openlocfilehash: bc322c704374374d6e7c075dbf466fc2b038b0ba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283214"
---
# <a name="benefits-and-tradeoffs-of-the-method-used-to-link-to-the-crt"></a>Vor- und Nachteile der Methode, um eine Verknüpfung zu der CRT

Das Projekt kann entweder dynamisch oder statisch mit der CRT verknüpft. In der folgenden Tabelle wird beschrieben, die vor- und Nachteile bei der Auswahl der zu verwendenden Methode.

|Methode|Vorteil|Tradeoff|
|------------|-------------|--------------|
|Mit der CRT verknüpft statisch.<br /><br /> (**Laufzeitbibliothek** festgelegt **Singlethread-**)|Die CRT-DLL ist nicht auf dem System erforderlich, in dem das Image ausgeführt wird.|Ca. 25 KB Startcode wird wesentlich erhöht die Größe des Abbilds, hinzugefügt.|
|Dynamisches Verknüpfen mit der CRT<br /><br /> (**Laufzeitbibliothek** festgelegt **mit mehreren Threads**)|Ihr Image erfordert keine den CRT-Startcode, daher ist es wesentlich kleiner ist.|Die CRT-DLL muss auf dem System, das Image ausführen.|

Das Thema [Verlinkung mit der CRT in ATL-Projekt](../atl/linking-to-the-crt-in-your-atl-project.md) wird erläutert, wie wählen Sie die Art und Weise, in dem mit der CRT verknüpft.

## <a name="see-also"></a>Siehe auch

[Programmieren mit ATL- und C-Laufzeitcode](../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[DLLs and Visual C++ run-time library behavior (Verhalten der Laufzeitbibliothek für DLLs und Visual C++)](../build/run-time-library-behavior.md)<br/>
[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
