---
title: Portieren von Drittanbieterbibliotheken
ms.date: 10/29/2019
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
ms.openlocfilehash: 89460af1ad0b356f4f5952141636a9f067131750
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627188"
---
# <a name="porting-third-party-libraries"></a>Portieren von Drittanbieterbibliotheken

Wenn Sie ein Projekt von Visual Studio 2013 oder einer früheren Version auf die aktuelle Version von C++Visual aktualisieren, müssen Sie auch alle Bibliotheken aktualisieren, die vom Projekt verwendet werden, sodass die Bibliothek und das Projekt mit der gleichen Version und dem gleichen Typ des Compilers erstellt werden. Wenn Sie keinen Zugriff auf den Quellcode der Bibliothek haben und die Bibliothek nicht über vcpkg verfügbar ist, müssen Sie vom Hersteller der Bibliothek eine aktualisierte Binärdatei abrufen. (Weitere Informationen finden Sie in der [Übersicht über potenzielle Probleme beim Upgrade](overview-of-potential-upgrade-issues-visual-cpp.md).)

Beim Upgrade einer Anwendung von Visual Studio 2015 oder Visual Studio 2017 auf Visual Studio 2019 ist es nicht notwendig, Abhängigkeiten zu aktualisieren, da der von diesen drei Versionen generierte Code binär kompatibel ist. Weitere Informationen finden [ C++ Sie unter binäre Kompatibilität zwischen Visual Studio 2015 und Visual Studio 2019](binary-compat-2015-2017.md).

## <a name="vcpkg-for-open-source-libraries"></a>vcpkg für Open-Source-Bibliotheken

In der Vergangenheit war das Auffinden und Aktualisieren von Drittanbieterbibliotheken mitunter nicht so einfach. Um C++ das Abrufen und Neuerstellen von Open Source-Bibliotheken von Drittanbietern zu vereinfachen, hat C++ das visuelle Team ein Befehlszeilen Tool mit dem Namen **VC + + Packaging Tool** oder **vcpkg**erstellt. vcpkg bietet einen durchsuchbaren Katalog mit vielen gängigen C++-Open-Source-Bibliotheken. Sie können eine beliebige Bibliothek im Katalog direkt über die Befehlszeile von vcpkg installieren. Bei der Installation einer Bibliothek erstellt vcpkg eine Verzeichnisstruktur auf dem Computer und fügt die H-, LIB- und Binärdateien diesem Ordner hinzu. Verwenden Sie diesen Ordner in der Kompilierungsbefehlszeile, oder integrieren Sie ihn in Visual Studio 2015 oder höher durch Ausführen des vcpkg-Installationsbefehls „integrate“. Nach der Integration eines Bibliotheksspeicherorts kann dieser von Visual Studio gefunden und neuen Projekten hinzugefügt werden, die Sie erstellen. Sie können eine Bibliothek verwenden, indem Sie sie mit `#include` hinzufügen. Visual Studio fügt dann den LIB-Pfad automatisch zu den Projekteinstellungen hinzu und kopiert die DLL-Datei in Ihren Projektmappenordner. Weitere Informationen finden Sie unter [vcpkg: A Package Manager for C++ (vcpkg: Ein Paket-Manager für C++)](../build/vcpkg.md).

## <a name="reporting-issues"></a>Melden von Problemen

Wenn Ihre Open-Source-Bibliothek nicht im **vcpkg** -Katalog vorhanden ist, können Sie ein Problem im [GitHub](https://github.com/Microsoft/vcpkg/issues) -Repository öffnen, in dem die C++ Community und das visuelle Team es sehen können, und möglicherweise die portdatei für diese Bibliothek erstellen.

## <a name="see-also"></a>Siehe auch

[Visual C++-Handbuch: Portieren und Aktualisieren](visual-cpp-porting-and-upgrading-guide.md)
