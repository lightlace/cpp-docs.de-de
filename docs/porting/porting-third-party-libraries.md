---
title: Portieren von Drittanbieterbibliotheken | Microsoft-Dokumentation
ms.custom: 
ms.date: 01/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
caps.latest.revision: 0
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: 1d85010b6068d52d8522875a3c47561ad777d345
ms.lasthandoff: 02/24/2017

---

# <a name="porting-third-party-libraries"></a>Portieren von Drittanbieterbibliotheken

Wenn Sie ein Projekt auf die aktuelle Version von Visual C++ aktualisieren, müssen Sie auch alle Bibliotheken aktualisieren, die das Projekt verwendet, damit Bibliothek und Projekt mit der gleichen Version und dem gleichen Typ des Compilers erstellt werden. (Weitere Informationen finden Sie in der [Übersicht über potenzielle Probleme beim Upgrade](overview-of-potential-upgrade-issues-visual-cpp.md).) 

## <a name="introducing-vcpkg"></a>Einführung in vcpkg
In der Vergangenheit war das Auffinden und Aktualisieren von Drittanbieterbibliotheken mitunter nicht so einfach. Um das Beziehen und Neuerstellen von C++-Open-Source-Bibliotheken von Drittanbietern zu erleichtern, hat das Visual C++-Team das Befehlszeilentool **VC++ Packaging Tool** bzw. **vcpkg** erstellt. vcpkg bietet einen durchsuchbaren Katalog mit vielen gängigen C++-Open-Source-Bibliotheken. Sie können eine beliebige Bibliothek im Katalog direkt über die Befehlszeile von vcpkg installieren. Bei der Installation einer Bibliothek erstellt vcpkg eine Verzeichnisstruktur auf dem Computer und fügt die H-, LIB- und Binärdateien diesem Ordner hinzu. Verwenden Sie diesen Ordner in der Kompilierungsbefehlszeile, oder integrieren Sie ihn in Visual Studio 2015 oder höher durch Ausführen des vcpkg-Installationsbefehls „integrate“. Nach der Integration eines Bibliotheksspeicherorts kann dieser von Visual Studio gefunden und neuen Projekten hinzugefügt werden, die Sie erstellen. Um eine Bibliothek zu verwenden, fügen Sie sie mit #include hinzu. Visual Studio fügt dann den LIB-Pfad Ihren Projekteinstellungen hinzu und kopiert die DLL in Ihren Projektmappenordner.

## <a name="acquisition-and-usage"></a>Download und Verwendung

Sie können vcpkg aus dem GitHub-Repository [vcpkg](https://github.com/Microsoft/vcpkg/) herunterladen.

 - So suchen Sie eine Bibliothek im Katalog: vcpkg search <LibName>
 - So rufen Sie eine Bibliothek ab (z.B. Boost): vcpkg install boost
 - So listen Sie die derzeit installierten Bibliotheken auf: vcpkg list

Im Blogbeitrag [Vcpkg: a tool to acquire and build C++ open source libraries on Windows](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) wird die Funktionsweise von vcpkg erläutert und eine Liste unterstützter Bibliotheken bereitgestellt. Die Liste wird wöchentlich aktualisiert.

## <a name="reporting-issues"></a>Melden von Problemen
Wenn Ihre Bibliothek nicht im vcpkg-Katalog vorhanden ist, können Sie ein Problem im [GitHub-Repository](https://github.com/Microsoft/vcpkg/issues) melden, in dem es der Community und dem Visual C++-Team angezeigt wird, um möglicherweise die Portierungsdatei für diese Bibliothek zu erstellen.

Für die geschützten (nicht Open-Source-) Bibliotheken von Drittanbietern empfehlen wir, den Bibliotheksanbieter zu kontaktieren. Wir möchten jedoch gerne von allen geschützten Bibliotheken wissen, die Sie nutzen und Sie blockieren. Informieren Sie uns unter vcupgrade@microsoft.com, von welchen Sie abhängig sind.

  
## <a name="see-also"></a>Siehe auch  
 [Visual C++-Handbuch: Portieren und Aktualisieren](visual-cpp-porting-and-upgrading-guide.md)

