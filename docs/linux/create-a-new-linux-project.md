---
title: Erstellen eines neuen C++ Linux-Projekts in Visual Studio | Microsoft Docs
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31309f961b392cb7548c3114e1af8604ac872cf3
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2017
---
# <a name="create-a-new-linux-project"></a>Erstellen eines neuen Linux-Projekts
Beim Codieren für Linux können Sie zwischen dem Erstellen eines Visual Studio-Projekts oder eines CMake-Projekts wählen. Dieses Thema beschreibt das Erstellen eines Visual Studio-Projekts. Informationen zu CMake-Projekten finden Sie unter [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md).

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

