---
title: Manifestgenerierung für C/C++-Programme
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: ff8d9f214b4fe4d004691c54474dcdabf2c0af85
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314740"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>Manifestgenerierung für C/C++-Programme

Ein [manifest](/windows/desktop/sbscs/manifests) ist ein XML-Dokument, die eine externe XML-Datei oder eine Ressource sein können, die in einer Anwendung oder eine Assembly eingebettet. Das Manifest eine [isolierte Anwendung](/windows/desktop/SbsCs/isolated-applications) wird verwendet, um die Verwaltung der Namen und Versionen freigegebener Seite-an-Seite-Assemblys, die an die die Anwendung zur Laufzeit gebunden werden soll. Das Manifest einer Seite-an-Seite-Assembly gibt seine Abhängigkeiten für Namen, Versionen, Ressourcen und anderen Assemblys.

Es gibt zwei Möglichkeiten, ein Manifest für isolierte Anwendung oder eine Seite-an-Seite-Assembly zu erstellen. Zunächst kann eine Manifestdatei Regeln befolgen, und nennen Sie die Anforderungen von der Verfasser der Assembly manuell erstellen. Auch wenn ein Programm nur auf Visual C++-Assemblys wie CRT, MFC, ATL oder anderen abhängig ist, kann dann ein Manifest automatisch vom Linker generiert werden.

Die Header der C++-Bibliotheken enthalten die Assemblyinformationen aus, und wenn Bibliotheken im Anwendungscode enthalten sind, wird diese Assemblyinformationen vom Linker ein Manifest für die endgültige Binärdatei bilden verwendet. Der Linker bettet die Manifestdatei in die Binärdatei nicht und kann nur das Manifest als externe Datei generieren. Müssen ein Manifest als externe Datei funktionieren nicht für alle Szenarien. Beispielsweise empfiehlt es sich, dass private Assemblys Manifeste eingebettet haben. In Befehlszeilenbuilds wie z. B. Dateien, die Nmake verwenden, um Code zu erstellen, kann ein Manifest mit dem Tool manifest eingebettet werden. Weitere Informationen finden Sie unter [Manifest Generation an der Befehlszeile](manifest-generation-at-the-command-line.md). Wenn Sie in Visual Studio zu erstellen, kann ein Manifest eingebettet werden, durch Festlegen einer Eigenschaft für das Manifesttool in die **Projekteigenschaften** Dialogfeld; Siehe [Manifest Generation in Visual Studio](manifest-generation-in-visual-studio.md).

## <a name="see-also"></a>Siehe auch

[Konzept der isolierten Anwendungen und der parallelen Assemblys](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
