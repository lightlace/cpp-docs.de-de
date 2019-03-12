---
title: Erstellen eines neuen C++ Projekts unter Linux in Visual Studio
ms.date: 09/12/2018
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: bd5ab1d2bc1077f366082bf8767f8f690173ac8b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57745162"
---
# <a name="create-a-new-linux-project"></a>Erstellen eines neuen Linux-Projekts

Stellen Sie zunächst sicher, dass Sie die **Workload „Linux-Entwicklung“** für Visual Studio installiert haben. Weitere Informationen finden Sie unter [Herunterladen, Installieren und Einrichten der Linux-Workload](download-install-and-setup-the-linux-development-workload.md).

Beim Erstellen eines neuen C++-Projekts in Visual Studio für Linux können Sie zwischen dem Erstellen eines Visual Studio-Projekts oder eines CMake-Projekts wählen. Dieses Thema beschreibt das Erstellen eines Visual Studio-Projekts. Informationen zum Arbeiten mit und Erstellen von CMake-Projekten finden Sie unter [Konfigurieren eines Linux CMake-Projekts](cmake-linux-project.md).

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
