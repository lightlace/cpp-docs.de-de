---
title: Portieren von Drittanbieterbibliotheken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/10/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e831f5441d62a4430fe036be70f1bec5ac99c98
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849716"
---
# <a name="porting-third-party-libraries"></a>Portieren von Drittanbieterbibliotheken

Wenn Sie ein Projekt auf die aktuelle Version von Visual C++ aktualisieren, müssen Sie auch alle Bibliotheken aktualisieren, die das Projekt verwendet, damit Bibliothek und Projekt mit der gleichen Version und dem gleichen Typ des Compilers erstellt werden. (Weitere Informationen finden Sie in der [Übersicht über potenzielle Probleme beim Upgrade](overview-of-potential-upgrade-issues-visual-cpp.md).) 

## <a name="introducing-vcpkg"></a>Einführung in vcpkg
In der Vergangenheit war das Auffinden und Aktualisieren von Drittanbieterbibliotheken mitunter nicht so einfach. Um das Beziehen und Neuerstellen von C++-Open-Source-Bibliotheken von Drittanbietern zu erleichtern, hat das Visual C++-Team das Befehlszeilentool **VC++ Packaging Tool** bzw. **vcpkg** erstellt. vcpkg bietet einen durchsuchbaren Katalog mit vielen gängigen C++-Open-Source-Bibliotheken. Sie können eine beliebige Bibliothek im Katalog direkt über die Befehlszeile von vcpkg installieren. Bei der Installation einer Bibliothek erstellt vcpkg eine Verzeichnisstruktur auf dem Computer und fügt die H-, LIB- und Binärdateien diesem Ordner hinzu. Verwenden Sie diesen Ordner in der Kompilierungsbefehlszeile, oder integrieren Sie ihn in Visual Studio 2015 oder höher durch Ausführen des vcpkg-Installationsbefehls „integrate“. Nach der Integration eines Bibliotheksspeicherorts kann dieser von Visual Studio gefunden und neuen Projekten hinzugefügt werden, die Sie erstellen. Um eine Bibliothek zu verwenden, fügen Sie sie mit #include hinzu. Visual Studio fügt dann den LIB-Pfad Ihren Projekteinstellungen hinzu und kopiert die DLL in Ihren Projektmappenordner. Weitere Informationen finden Sie unter [vcpkg: A Package Manager for C++ (vcpkg: Ein Paket-Manager für C++)](../vcpkg.md).


## <a name="reporting-issues"></a>Melden von Problemen
Wenn Ihre Bibliothek nicht im vcpkg-Katalog vorhanden ist, können Sie ein Problem im [GitHub-Repository](https://github.com/Microsoft/vcpkg/issues) melden, in dem es der Community und dem Visual C++-Team angezeigt wird, um möglicherweise die Portierungsdatei für diese Bibliothek zu erstellen.

Für die geschützten (nicht Open-Source-) Bibliotheken von Drittanbietern empfehlen wir, den Bibliotheksanbieter zu kontaktieren. Wir möchten jedoch gerne von allen geschützten Bibliotheken wissen, die Sie nutzen und Sie blockieren. Informieren Sie uns unter vcupgrade@microsoft.com, von welchen Sie abhängig sind.

  
## <a name="see-also"></a>Siehe auch  
 [Visual C++-Handbuch: Portieren und Aktualisieren](visual-cpp-porting-and-upgrading-guide.md)
