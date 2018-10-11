---
title: Binärdateienkompatibilität zwischen Visual Studio 2015 und Visual Studio 2017 | Microsoft Docs
ms.custom: ''
ms.date: 09/24/2018
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4cedef2d5343b93c544ab22c41d2e5ac661bc3dd
ms.sourcegitcommit: edb46b0239a0e616af4ec58906e12338c3e8d2c6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47169566"
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Binärdateienkompatibilität zwischen Visual Studio 2015 und Visual Studio 2017

In früheren Versionen von Visual Studio war die Binärdateienkompatibilität zwischen Objektdateien (OBJ-Dateien), statischen Bibliotheken (LIB-Dateien), dynamischen Bibliotheken (DLL-Dateien) und ausführbaren Dateien (EXE-Dateien), die unter Verwendung verschiedener Versionen des Compilertoolsets und der Laufzeitbibliotheken erstellt wurden, nicht gewährleistet. Dies hat sich in Visual Studio 2017 geändert. In Visual Studio 2015 und Visual Studio 2017 ist die Hauptversion des C++-Toolsets 14 (v140 für Visual Studio 2015 und v141 für Visual Studio 2017). Dies spiegelt die Tatsache wider, dass sowohl die Laufzeitbibliotheken als auch die Anwendungen, die mit einer der beiden Versionen des Compilers kompiliert wurden, (größtenteils) binärdateienkompatibel sind. Wenn Sie eine DLL in Visual Studio 2015 erstellt haben, bedeutet dies beispielsweise, dass diese nicht erneut kompiliert werden muss, um sie aus einer Anwendung zu nutzen, die mit Visual Studio 2017 erstellt wurde.  

Für diese Regel gelten zwei Ausnahmen: Die Binärdateienkompatibilität ist in diesen Fällen nicht gewährleistet:  

1. Wenn statische Bibliotheken oder Objektdateien mit dem Compilerschalter `/GL` kompiliert werden.  

2. Beim Verwenden von Bibliotheken, die mit einem Toolset erstellt wurden, dessen Version höher als die Version des Toolsets ist, das zum Kompilieren und Verknüpfen der Anwendung verwendet wurde. Beispielsweise kann ein Programm, das mit der Compilerversion 19.12 kompiliert und verknüpft wurde, Bibliotheken nutzen, die mit Version 19.0 bis 19.12 kompiliert wurden. Außerdem besteht Binärdateienkompatibilität nur zwischen Visual Studio 2015 und Visual Studio 2017. Die Verknüpfung von 19.x-Programmen mit Bibliotheken, die mit Visual Studio 2013 oder früher erstellt wurden, wird nicht unterstützt.

## <a name="see-also"></a>Siehe auch  

[Änderungsverlauf von Visual C++](..\porting\visual-cpp-change-history-2003-2015.md)
