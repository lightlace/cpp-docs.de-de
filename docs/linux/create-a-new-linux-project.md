---
title: Erstellen eines neuen C++ Projekts unter Linux in Visual Studio
ms.date: 10/24/2019
description: Erstellen Sie ein neues MSBuild-basiertes Linux-Projekt in Visual Studio.
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 5d5fa67566d86edb2ed0389fdbe38866b47e2211
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626720"
---
# <a name="create-a-new-linux-project"></a>Erstellen eines neuen Linux-Projekts

::: moniker range="vs-2015"

Linux-Projekte sind in Visual Studio 2017 und höher verfügbar.

::: moniker-end

::: moniker range="vs-2017"

Stellen Sie zunächst sicher, dass Sie die **Workload „Linux-Entwicklung“** für Visual Studio installiert haben. Weitere Informationen finden Sie unter [Herunterladen, Installieren und Einrichten der Linux-Workload](download-install-and-setup-the-linux-development-workload.md).

Für eine plattformübergreifende Kompilierung wird die Verwendung von CMake empfohlen. CMake wird in Visual Studio 2019 umfassender unterstützt. Wenn CMake nicht verwendet werden kann und Sie über eine vorhandene Visual Studio-Projektmappe für Windows verfügen, die Sie für die Kompilierung unter Linux erweitern möchten, können Sie der Windows-Projektmappe ein Visual Studio-Projekt für Linux sowie ein Projekt für **freigegebene Elemente** hinzufügen. Platzieren Sie den von beiden Plattformen gemeinsam verwendeten Code im Projekt „Freigegebene Elemente“, und fügen Sie für die Windows- und Linux-Projekte einen Verweis auf dieses Projekt hinzu.

## <a name="to-create-a-new-linux-project"></a>So erstellen Sie ein neues Linux-Projekts

Führen Sie folgende Schritte aus, um ein neues Linux-Projekt in Visual Studio 2017 zu erstellen:

1. Wählen Sie in Visual Studio **Datei > Neues Projekt** aus, oder drücken Sie **STRG + UMSCHALT + N**.
1. Wählen Sie **Visual C++ > Plattformübergreifend > Linux** und anschließend den Projekttyp aus, den Sie erstellen möchten. Geben Sie einen **Namen** und einen **Speicherort** an, und klicken Sie dann auf **OK**.

   ![Neues Linux-Projekt](media/newproject.png)

   | Projekttyp | BESCHREIBUNG |
   | ------------ | --- |
   | **Blink (Raspberry)**           | Projekt für ein Raspberry Pi-Gerät mit Beispielcode für das Aufblinken einer LED |
   | **Konsolenanwendung (Linux)** | Projekt für alle Linux-Computer mit Beispielcode für die Ausgabe von Text an die Konsole |
   | **Leeres Projekt (Linux)**       | Projekt für alle Linux-Computer ohne Beispielcode |
   | **Makefile-Projekt (Linux)**    | Projekt für alle Linux-Computer, die mithilfe eines Standard-Makefile-Buildsystems erstellt wurden |

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren eines Linux-Projekts](configure-a-linux-project.md)

::: moniker-end

::: moniker range="vs-2019"

Stellen Sie zunächst sicher, dass Sie die **Workload „Linux-Entwicklung“** für Visual Studio installiert haben. Weitere Informationen finden Sie unter [Herunterladen, Installieren und Einrichten der Linux-Workload](download-install-and-setup-the-linux-development-workload.md).

Wenn Sie ein neues C++-Projekt für Linux in Visual Studio erstellen, können Sie zwischen einem Visual Studio- und einem CMake-Projekt wählen. In diesem Artikel wird beschrieben, wie Sie ein Visual Studio-Projekt erstellen können. Im Allgemeinen empfiehlt sich für neue Projekte, die möglicherweise Open-Source-Code enthalten oder für die plattformübergreifende Entwicklung kompiliert werden sollen, die Verwendung von CMake mit Visual Studio. Mithilfe eines CMake-Projekts können Sie dasselbe Projekt sowohl für Windows als auch für Linux erstellen und debuggen. Weitere Informationen finden Sie unter [Erstellen und Konfigurieren eines Linux-CMake-Projekts](cmake-linux-project.md).

Wenn Sie über eine vorhandene Visual Studio-Projektmappe für Windows verfügen, die Sie für die Kompilierung unter Linux erweitern möchten, und CMake nicht verwendet werden kann, können Sie der Windows-Projektmappe ein Visual Studio-Projekt für Linux sowie ein Projekt für **freigegebene Elemente** hinzufügen. Platzieren Sie den von beiden Plattformen gemeinsam verwendeten Code im Projekt „Freigegebene Elemente“, und fügen Sie für die Windows- und Linux-Projekte einen Verweis auf dieses Projekt hinzu.

## <a name="to-create-a-new-linux-project"></a>So erstellen Sie ein neues Linux-Projekts

Führen Sie folgende Schritte aus, um ein neues Linux-Projekt in Visual Studio 2019 zu erstellen:

1. Wählen Sie in Visual Studio **Datei > Neues Projekt** aus, oder drücken Sie **STRG + UMSCHALT + N**.
1. Legen Sie die **Sprache** auf **C++** fest, und suchen Sie nach „Linux“. Wählen Sie den zu erstellenden Projekttyp aus, und klicken Sie dann auf **Weiter**. Geben Sie einen **Namen** und einen **Speicherort** an, und klicken Sie auf **Erstellen**.

   ![Neues Linux-Projekt](media/newproject-vs2019.png)

   | Projekttyp | BESCHREIBUNG |
   | ------------ | --- |
   | **Blink (Raspberry)**           | Projekt für ein Raspberry Pi-Gerät mit Beispielcode für das Aufblinken einer LED |
   | **Konsolenanwendung (Linux)** | Projekt für alle Linux-Computer mit Beispielcode für die Ausgabe von Text an die Konsole |
   | **Leeres Projekt (Linux)**       | Projekt für alle Linux-Computer ohne Beispielcode |
   | **Makefile-Projekt (Linux)**    | Projekt für alle Linux-Computer, die mithilfe eines Standard-Makefile-Buildsystems erstellt wurden |

## <a name="next-steps"></a>Nächste Schritte

[Konfigurieren eines Linux-Projekts](configure-a-linux-project.md)

::: moniker-end
