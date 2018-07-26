---
title: Erstellen eines neuen C++ Linux-Projekts in Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 07/20/2018
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
ms.openlocfilehash: f64f8eaf09e92df3dd776180db5904af039d6ad7
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207969"
---
# <a name="create-a-new-linux-project"></a>Erstellen eines neuen Linux-Projekts
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

