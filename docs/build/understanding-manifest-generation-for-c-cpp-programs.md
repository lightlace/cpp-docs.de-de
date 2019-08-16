---
title: Manifestgenerierung für C/C++-Programme
ms.date: 11/04/2016
helpviewer_keywords:
- manifests [C++]
ms.assetid: a1f24221-5b09-4824-be48-92eae5644b53
ms.openlocfilehash: 16d5efc5c5f7ce81b4b60269b0c666fd5d24266e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492527"
---
# <a name="understanding-manifest-generation-for-cc-programs"></a>Manifestgenerierung für C/C++-Programme

Ein [Manifest](/windows/win32/sbscs/manifests) ist ein XML-Dokument, das eine externe XML-Datei oder eine Ressource sein kann, die in einer Anwendung oder einer Assembly eingebettet ist. Das Manifest einer [isolierten Anwendung](/windows/win32/SbsCs/isolated-applications) wird verwendet, um die Namen und Versionen von freigegebenen parallelen Assemblys zu verwalten, an die die Anwendung zur Laufzeit gebunden werden soll. Das Manifest einer parallelen Assembly gibt die Abhängigkeiten von Namen, Versionen, Ressourcen und anderen Assemblys an.

Es gibt zwei Möglichkeiten, ein Manifest für eine isolierte Anwendung oder eine parallele Assembly zu erstellen. Zuerst kann der Autor der Assembly nach den Regeln und Benennungs Anforderungen manuell eine Manifest-Datei erstellen. Wenn ein Programm nur von visuellen C++ Assemblys wie CRT, MFC, ATL oder anderen abhängig ist, kann ein Manifest automatisch vom Linker generiert werden.

Die Header von visuellen C++ Bibliotheken enthalten Assemblyinformationen, und wenn die Bibliotheken im Anwendungscode enthalten sind, werden diese Assemblyinformationen vom Linker verwendet, um ein Manifest für die endgültige Binärdatei zu bilden. Der Linker bettet die Manifestressource nicht in die Binärdatei ein und kann das Manifest nur als externe Datei generieren. Das vorhanden sein eines Manifests als externe Datei funktioniert möglicherweise nicht für alle Szenarien. Es wird z. b. empfohlen, dass private Assemblys eingebettete Manifeste aufweisen. In Befehlszeilenbuilds wie z. b. solchen, die NMAKE verwenden, um Code zu erstellen, kann ein Manifest mit dem Manifest-Tool eingebettet werden. Weitere Informationen finden Sie [unter Generierung von Manifesten in der Befehlszeile](manifest-generation-at-the-command-line.md). Beim Aufbau in Visual Studio kann ein Manifest eingebettet werden, indem im Dialogfeld " **Projekteigenschaften** " eine Eigenschaft für das Manifest-Tool festgelegt wird. Weitere Informationen finden Sie [unter Manifest-Generierung in Visual Studio](manifest-generation-in-visual-studio.md).

## <a name="see-also"></a>Siehe auch

[Konzept der isolierten Anwendungen und der parallelen Assemblys](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[Erstellen von isolierten Anwendungen und parallelen Assemblys (C/C++)](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
