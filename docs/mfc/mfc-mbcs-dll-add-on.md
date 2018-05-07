---
title: MFC MBCS DLL-Add-On | Microsoft Docs
ms.custom: ''
ms.date: 1/04/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MBCS
- MFC
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df6ecf03a5b1c92dc7e435fc014615db09422638
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL-Add-On

Unterstützung für die MFC und Mehrbyte-Zeichensätzen (MBCS)-Satz Bibliotheken werden während der Installation von Visual Studio in Visual Studio 2013 2015 und 2017 ein zusätzlicher Schritt erforderlich.

**Visual Studio 2013**: standardmäßig die MFC-Bibliotheken in Visual Studio 2013 installiert nur Unicode-Entwicklung unterstützt. Sie benötigen die MBCS-DLLs aus, um ein MFC-Projekt in Visual Studio 2013 zu erstellen, bei der **Zeichensatz** -Eigenschaftensatz auf **Multi-Byte-Zeichensatz verwenden** oder **nicht festgelegt**. Herunterladen der DLL [Multibyte-MFC-Bibliothek für Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: sowohl Unicode-als auch MBCS MFC-DLLs sind in der Visual C++-Setup-Komponenten enthalten, aber die Unterstützung für MFC nicht standardmäßig installiert ist. Visual C++ und MFC sind optionale Installationskonfigurationen beim Visual Studio-Setup. Um sicherzustellen, dass MFC installiert wird, wählen Sie im Setup **Benutzerdefiniert** aus. Unter **Programmiersprachen**stellen Sie dann sicher, dass die Optionen **Visual C++** und **Microsoft Foundation Classes für C++** ausgewählt sind. Wenn Sie Visual Studio bereits installiert haben, werden Sie aufgefordert, Visual C++ und/oder MFC zu installieren, wenn Sie versuchen, ein MFC-Projekt zu erstellen.

**Visual Studio-2017**: der Unicode- und MBCS MFC-DLLs installiert sind, mit der **Desktopentwicklung mit C++** Arbeitslast bei der Auswahl **MFC- und ATL-Unterstützung** aus der **Optional Komponenten** Bereich. Wenn die Installation dieser Komponenten nicht enthalten ist, können, starten Sie den Installer von der **neue Projekte** Dialogfeld mithilfe der **Installer für Visual Studio öffnen** Link.

## <a name="see-also"></a>Siehe auch

[MFC-Bibliotheksversionen](../mfc/mfc-library-versions.md)

