---
title: Kompatibilität von C++-Binärdateien zwischen Visual Studio 2015 und Visual Studio 2019
ms.date: 05/03/2019
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
ms.openlocfilehash: 052874eb9273ee9a9ce1695ffdadedd9911673e1
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65449046"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2019"></a>Kompatibilität von C++-Binärdateien zwischen Visual Studio 2015 und Visual Studio 2019

In Visual Studio 2013 und früheren Versionen war die Binärdateienkompatibilität zwischen Objektdateien (OBJ-Dateien), statischen Bibliotheken (LIB-Dateien), dynamischen Bibliotheken (DLL-Dateien) und ausführbaren Dateien (EXE-Dateien), die unter Verwendung verschiedener Versionen des Compilertoolsets und der Runtimebibliotheken erstellt wurden, nicht gewährleistet. 

In Visual Studio 2015 und höheren Versionen ist die Hauptversion des C++-Toolsets 14 (v140 für Visual Studio 2015, v141 für Visual Studio 2017 und v142 für Visual Studio 2019). Dies spiegelt die Tatsache wider, dass sowohl die Runtimebibliotheken als auch die Anwendungen, die mit einer der beiden Versionen des Compilers kompiliert wurden, binärdateienkompatibel sind. Dies bedeutet, dass Sie eine mit Visual Studio 2015 erstellte Drittanbieterbibliothek nicht noch mal kompilieren müssen, um sie aus einer Anwendung zu nutzen, die mit Visual Studio 2017 oder Visual Studio 2019 erstellt wurde.

Die einzige Ausnahme dieser Regel sind mit dem `/GL`-Compilerschalter kompilierte statische Bibliotheken oder Objektdateien, die nicht binärkompatibel sind. 

Wenn Sie Binärdateien kombinieren, die mit verschiedenen unterstützten Versionen des MSVC-Toolsets erstellt wurden, kann das Visual C++ Redistributable-Paket, auf dem Ihre Anwendung ausgeführt wird, nicht älter als die Toolsetversionen sein, die zum Erstellen Ihrer App oder der verarbeiteten Bibliotheken verwendet werden. 

## <a name="see-also"></a>Siehe auch

[Änderungsverlauf von Visual C++](../porting/visual-cpp-change-history-2003-2015.md)
