---
title: "Binärdateienkompatibilität zwischen Visual Studio 2015 und Visual Studio 2017 | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f534432fbf7ff723cac1448bc3a26474f3b323bb
ms.sourcegitcommit: c770a343def04ae77522708387c3f7c470e49969
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2018
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Binärdateienkompatibilität zwischen Visual Studio 2015 und Visual Studio 2017


In früheren Versionen von Visual Studio war die Binärdateienkompatibilität zwischen Objektdateien (OBJ-Dateien), statischen Bibliotheken (LIB-Dateien), dynamischen Bibliotheken (DLL-Dateien) und ausführbaren Dateien (EXE-Dateien), die unter Verwendung verschiedener Versionen des Compilertoolsets und der Laufzeitbibliotheken erstellt wurden, nicht gewährleistet. Dies hat sich in Visual Studio 2017 geändert. In Visual Studio 2015 und Visual Studio 2017 ist die Hauptversion des C++-Toolsets 14 (v140 für Visual Studio 2015 und v141 für Visual Studio 2017). Dies spiegelt die Tatsache wider, dass sowohl die Laufzeitbibliotheken als auch die Anwendungen, die mit einer der beiden Versionen des Compilers kompiliert wurden, (größtenteils) binärdateienkompatibel sind. Das bedeutet, dass Sie z.B. eine DLL in Visual Studio 2017 erstellen und aus einer mit Visual Studio 2015 kompilierten Anwendung verwenden können, oder dass Sie die weiterverteilbaren Bibliotheken von Visual Studio 2017 mit Ihrer Anwendung verwenden können, die mit dem Toolset der Version 2015 erstellt wurde.  

Für diese Regel gelten zwei Ausnahmen: Die Binärdateienkompatibilität ist in diesen Fällen nicht gewährleistet:  

1) Wenn statische Bibliotheken oder Objektdateien mit dem Compilerschalter /GL kompiliert werden.  

2) Beim Verwenden von Bibliotheken, die mit einem Toolset erstellt wurden, dessen Version höher als die Version des Toolsets ist, das zum Kompilieren und Verknüpfen der Anwendung verwendet wurde. Zum Beispiel kann ein Programm, das mit dem Toolset 19.12 kompiliert und verknüpft wurde, Bibliotheken verwenden, die mit einem Toolset der Version 19.0 bis 19.12 kompiliert wurden. Das Verknüpfen von Programmen in Version 19.x wird nicht mit Bibliotheken unterstützt, die in Visual Studio 2013 oder früher erstellt wurden.


## <a name="see-also"></a>Siehe auch  

[Änderungsverlauf von Visual C++](..\porting\visual-cpp-change-history-2003-2015.md)


