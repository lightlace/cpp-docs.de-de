---
title: MFC MBCS DLL-Add-On | Microsoft Docs
ms.custom: 
ms.date: 08/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MBCS
- MFC
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 176ed47b4d6a799cf53d2a1cea8cb232f1c2c4aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-mbcs-dll-add-on"></a>MFC MBCS DLL-Add-On
 Sie benötigen die Multibyte-DLL-Dateien, um ein MFC-Projekt in Visual Studio 2015 zu erstellen, bei dem die **Zeichensatz** -Eigenschaft auf **Multi-Byte-Zeichensatz verwenden** oder **Nicht festgelegt**eingestellt ist.  

**Visual Studio 2013**: Laden der DLL [Multibyte-MFC-Bibliothek für Visual Studio 2013](https://www.microsoft.com/en-us/download/details.aspx?id=40770).

**Visual Studio 2015**: die DLL ist in der Visual C++-Setup-Komponenten enthalten. Visual C++ und MFC sind optionale Installationskonfigurationen beim Visual Studio-Setup. Um sicherzustellen, dass MFC installiert wird, wählen Sie im Setup **Benutzerdefiniert** aus. Unter **Programmiersprachen**stellen Sie dann sicher, dass die Optionen **Visual C++** und **Microsoft Foundation Classes für C++** ausgewählt sind. Wenn Sie Visual Studio bereits installiert haben, werden Sie aufgefordert, Visual C++ und/oder MFC zu installieren, wenn Sie versuchen, ein MFC-Projekt zu erstellen.  
  
**Visual Studio-2017**: die DLL installiert ist, mit der **mit C++-Desktopentwicklung** Arbeitslast bei der Auswahl **MFC- und ATL-Unterstützung** aus der **optionalen Komponenten** Bereich.

  
## <a name="see-also"></a>Siehe auch  
 [MFC-Bibliotheksversionen](../mfc/mfc-library-versions.md)

