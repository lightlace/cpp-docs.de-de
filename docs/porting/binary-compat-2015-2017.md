---
title: C++-Binärkompatibilität von 2015 bis 2019
description: Beschreibt, wie die binäre Kompatibilität zwischen C++ kompilierten Dateien in Visual Studio 2015, 2017 und 2019 funktioniert. Ein Microsoft Visual C++ Redistributable Package funktioniert für alle drei Versionen.
ms.date: 11/18/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: b729cdcc4a494e60ec58314fe23b02c1816e8412
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188788"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-2017-and-2019"></a>C++binäre Kompatibilität zwischen Visual Studio 2015, 2017 und 2019

Die Microsoft C++ -compilertoolsets (MSVC) in Visual Studio 2013 und früheren Versionen garantieren keine Versions übergreifende binäre Kompatibilität. Sie können Objektdateien, statische Bibliotheken, dynamische Bibliotheken und ausführbare Dateien, die von verschiedenen Versionen erstellt wurden, nicht verknüpfen. Die ABIS-, Objekt Format-und Laufzeitbibliotheken sind nicht kompatibel.

Wir haben dieses Verhalten in Visual Studio 2015, 2017 und 2019 geändert. Die Laufzeitbibliotheken und-apps, die von einer dieser Versionen des Compilers kompiliert werden, sind binär kompatibel. Dies wird in der Haupt C++ Nummer des Toolsets widergespiegelt, bei der es sich um 14 für alle drei Versionen handelt. (Die Toolsetversion ist V140 für Visual Studio 2015, v141 für 2017 und v142 für 2019). Nehmen wir an, Sie haben Bibliotheken von Drittanbietern, die von Visual Studio 2015 erstellt wurden. Sie können Sie weiterhin in einer Anwendung verwenden, die von Visual Studio 2017 oder 2019 erstellt wurde. Es ist nicht erforderlich, mit einem passenden Toolset neu zu kompilieren. Die neueste Version des Microsoft Visual C++ Redistributable Package (verteilbares Paket) funktioniert für alle.

Es gibt drei wichtige Einschränkungen hinsichtlich der Binärkompatibilität:

- Sie können Binärdateien mischen, die von verschiedenen Versionen des Toolsets erstellt wurden. Sie müssen jedoch ein Toolset mit mindestens der aktuellen Binärdatei verwenden, um Ihre APP zu verknüpfen. Hier ist ein Beispiel: Sie können eine mit dem 2017-Toolset kompilierte App mit einer statischen Bibliothek verknüpfen, die mit 2019 kompiliert wurde, wenn Sie mit dem 2019-Toolset verknüpft sind.

- Die von Ihrer APP verwendete verteilbare Einschränkung hat eine ähnliche Einschränkung der Binärkompatibilität. Wenn Sie Binärdateien mischen, die von verschiedenen unterstützten Versionen des Toolsets erstellt wurden, muss die verteilbare Version mindestens so neu sein wie das neueste Toolset, das von einer beliebigen App-Komponente verwendet wird.

- Statische Bibliotheken oder Objektdateien, die mit dem Compilerschalter [/GL (gesamte Programm Optimierung)](../build/reference/gl-whole-program-optimization.md) kompiliert wurden, *sind nicht* zwischen verschiedenen Versionen binär kompatibel. Alle Objektdateien und Bibliotheken, die mit `/GL` kompiliert wurden, müssen genau das gleiche Toolset für die Kompilierung und den endgültigen Link verwenden.

## <a name="upgrade-the-microsoft-visual-c-redistributable-from-visual-studio-2015-or-2017-to-visual-studio-2019"></a>Upgrade von Microsoft Visual C++ Redistributable von Visual Studio 2015 oder 2017 auf Visual Studio 2019

Wir haben die Hauptversionsnummer C++ von Microsoft Visual Redistributable für Visual Studio 2015, 2017 und 2019 beibehalten. Dies bedeutet, dass jeweils nur eine Instanz der verteilbaren Komponente installiert werden kann. Eine neuere Version überschreibt jede ältere Version, die bereits installiert ist. Beispielsweise kann eine APP die verteilbare Komponente von Visual Studio 2015 installieren. Anschließend wird das verteilbare Element von einer anderen APP aus Visual Studio 2019 installiert. Die Version 2019 überschreibt die ältere Version, aber da sie binär kompatibel sind, funktioniert die frühere App weiterhin einwandfrei. Wir stellen sicher, dass die neueste Version der verteilbaren Version alle neuesten Features, Sicherheitsupdates und Fehlerbehebungen enthält. Aus diesem Grund empfehlen wir immer, ein Upgrade auf die neueste verfügbare Version durchzuführen.

Auf ähnliche Weise können Sie keine ältere verteilbare Komponente installieren, wenn bereits eine neuere Version installiert ist. Wenn Sie versuchen, meldet das Installationsprogramm einen Fehler. Ein solcher Fehler wird angezeigt, wenn Sie das verteilbare 2015-oder 2017-Paket auf einem Computer installieren, auf dem bereits die Version 2019 vorhanden ist:

```Output
0x80070666 - Another version of this product is already installed. Installation of this version cannot continue. To configure or remove the existing version of this product, use Add/Remove Programs on the Control Panel.
```

Dieser Fehler ist Entwurfs bedingt. Es wird empfohlen, die neueste Version zu installieren. Stellen Sie sicher, dass das Installationsprogramm den Fehler automatisch wiederherstellen kann.

## <a name="see-also"></a>Siehe auch

[Visueller C++ Änderungs Verlauf](../porting/visual-cpp-change-history-2003-2015.md)\
[Die neuesten unterstützten C++ visuellen verteilbaren Downloads](https://support.microsoft.com/help/2977003/the-latest-supported-visual-c-downloads)
