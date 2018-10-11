---
title: Erstellen eines neuen C++ Linux-Projekts in Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: 2386d89afcd566dac77f62cd0afc36e5952674ab
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601417"
---
# <a name="create-a-new-linux-project"></a>Erstellen eines neuen Linux-Projekts

Stellen Sie zunächst sicher, dass Sie die **Workload „Linux-Entwicklung“** für Visual Studio installiert haben. Weitere Informationen finden Sie unter [Herunterladen, Installieren und Einrichten der Linux-Workload](download-install-and-setup-the-linux-development-workload.md).

Beim Codieren von C++ in Visual Studio für Linux können Sie zwischen dem Erstellen eines Visual Studio-Projekts oder eines CMake-Projekts wählen. Dieses Thema beschreibt das Erstellen eines Visual Studio-Projekts. Informationen zu CMake-Projekten finden Sie unter [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md).

Um ein neues Linux-Projekt in Visual Studio zu erstellen, führen Sie folgende Schritte aus:

1. Wählen Sie in Visual Studio **Datei > Neues Projekt** aus, oder drücken Sie **STRG + UMSCHALT + N**.
1. Wählen Sie den Knoten unter **Visual C++ > Plattformübergreifend > Linux** und anschließend den Projekttyp aus, den Sie erstellen möchten. Geben Sie einen Namen und Speicherort ein, und klicken Sie auf „OK“.

   ![Neues Linux-Projekt](media/newproject.png)

   | Projekttyp | Beschreibung 
   | ------------ | ---
   | **Blink (Raspberry)**           | Projekt für ein Raspberry Pi-Gerät mit Beispielcode für das Aufblinken einer LED
   | **Konsolenanwendung (Linux)** | Projekt für alle Linux-Computer mit Beispielcode für die Ausgabe von Text an die Konsole
   | **Leeres Projekt (Linux)**       | Projekt für alle Linux-Computer ohne Beispielcode
   | **Makefile-Projekt (Linux)**    | Projekt für alle Linux-Computer, die mithilfe eines Standard-Makefile-Buildsystems erstellt werden

