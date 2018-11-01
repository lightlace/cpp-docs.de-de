---
title: MFC MBCS DLL-Add-On
ms.date: 1/04/2018
helpviewer_keywords:
- MBCS
- MFC
ms.openlocfilehash: a78425ac92aa9ddfe7f0b1b61dde915b3e088383
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558912"
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL-Add-On

Unterstützung für MFC und dessen Multibytezeichen-Satz (MBCS)-Bibliotheken müssen einen zusätzlichen Schritt während der Installation von Visual Studio in Visual Studio 2013, 2015 und 2017.

**Visual Studio 2013**: Standardmäßig unterstützen MFC-Bibliotheken in Visual Studio 2013 installiert nur Unicode-Entwicklung. Sie benötigen die MBCS-DLLs aus, um ein MFC-Projekt in Visual Studio 2013 zu erstellen, die die **Zeichensatz** -Eigenschaft auf festgelegt **Multi-Byte-Zeichensatz verwenden** oder **Nenastaveno**. Laden Sie die DLL zur [Multibyte-MFC-Bibliothek für Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40770).

**Visual Studio 2015**: sowohl Unicode-als auch MBCS MFC-DLLs sind in den Visual C++-Setupkomponenten enthalten die Unterstützung für MFC nicht standardmäßig installiert ist. Visual C++ und MFC sind optionale Installationskonfigurationen beim Visual Studio-Setup. Um sicherzustellen, dass MFC installiert wird, wählen Sie im Setup **Benutzerdefiniert** aus. Unter **Programmiersprachen**stellen Sie dann sicher, dass die Optionen **Visual C++** und **Microsoft Foundation Classes für C++** ausgewählt sind. Wenn Sie Visual Studio bereits installiert haben, werden Sie aufgefordert, Visual C++ und/oder MFC zu installieren, wenn Sie versuchen, ein MFC-Projekt zu erstellen.

**Visual Studio 2017**: die Unicode und MBCS MFC-DLLs installiert sind, mit der **Desktopentwicklung mit C++** Workload, die bei der Auswahl **MFC- und ATL-Unterstützung** aus der **Optional Komponenten** Bereich. Wenn Ihre Installation dieser Komponenten nicht enthalten ist, navigieren Sie zu der **Datei | Neue Projekte** Dialogfeld und klicken Sie auf die **Visual Studio-Installer öffnen** Link.

## <a name="see-also"></a>Siehe auch

[MFC-Bibliotheksversionen](../mfc/mfc-library-versions.md)

