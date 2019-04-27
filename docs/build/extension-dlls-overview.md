---
title: 'Erweiterungs-DLLs: Übersicht'
ms.date: 11/04/2016
helpviewer_keywords:
- AFXDLL library
- MFC DLLs [C++], MFC extension DLLs
- DLLs [C++], extension
- shared DLL versions [C++]
- extension DLLs [C++], about MFC extension DLLs
ms.assetid: eb5e10b7-d615-4bc7-908d-e3e99b7b1d5f
ms.openlocfilehash: ab9b980cbb3e89eebee945e90c54f23d6717a1a4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196728"
---
# <a name="mfc-extension-dlls-overview"></a>MFC-Erweiterungs-DLLs: Übersicht

Eine MFC-Erweiterungs-DLL ist eine DLL, in der Regel wiederverwendbare von bestehenden Microsoft Foundation Class Library-Klassen abgeleitete Klassen implementiert. MFC-Erweiterungs-DLLs werden mit der Dynamic Link Library-Version von MFC (auch bekannt als die freigegebene Version von MFC) erstellt. MFC-Dateien (entweder Anwendungen oder regulären MFC-DLLs), die mit die freigegebene Version von MFC integriert sind, können eine MFC-Erweiterungs-DLL. Mit einer MFC-Erweiterungs-DLL können Sie neue benutzerdefinierte Klassen von MFC ableiten und dann anbieten dieser erweiterte Version von MFC für Anwendungen, die die DLL aufrufen.

Erweiterungs-DLLs können auch dazu verwendet werden, von MFC abgeleitete Objekte zwischen Anwendung und DLL zu übergeben. Die dem übergebenen Objekt zugeordneten Memberfunktionen befinden sich in dem Modul, in dem das Objekt erstellt wurde. Da diese Funktionen bei Verwendung der freigegebene DLL-Version von MFC ordnungsgemäß exportiert werden, können Sie kostenlos MFC übergeben oder Zeiger von MFC abgeleitete Objekte zwischen einer Anwendung und der MFC-Erweiterungs-DLLs geladen.

Ein Beispiel für eine DLL, die die grundlegenden Voraussetzungen für eine MFC-Erweiterungs-DLL erfüllt, finden Sie im MFC-Beispiel [DLLHUSK](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/dllhusk). Betrachten Sie insbesondere die Testdll1.cpp und Testdll2.cpp-Dateien.

Beachten Sie, die den Begriff diese Bezeichnung nicht mehr in der Dokumentation zu Visual C++ verwendet wird. Eine MFC-Erweiterungs-DLL hat die gleichen Eigenschaften wie die frühere AFXDLL.

## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [MFC-Erweiterungs-DLLs initialisieren](run-time-library-behavior.md#initializing-extension-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [MFC extension DLLs (MFC-Erweiterungs-DLLs)](extension-dlls.md)

- [Using Database, OLE, and Sockets MFC extension DLLs in regular MFC DLLs (Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs)](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC-fremde DLLs: Übersicht](non-mfc-dlls-overview.md)

- [Reguläre, statisch mit MFC verknüpfte MFC-DLLs](regular-dlls-statically-linked-to-mfc.md)

- [Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs](regular-dlls-dynamically-linked-to-mfc.md)

- [Erstellen eine MFC-DLL](../mfc/reference/mfc-dll-wizard.md)

## <a name="see-also"></a>Siehe auch

[Arten von DLLs](kinds-of-dlls.md)
