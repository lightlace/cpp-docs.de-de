---
title: 'Vorgehensweise: Erstellen überprüfbarer C++-Projekte (C++ / CLI)'
ms.date: 11/04/2016
helpviewer_keywords:
- verifiable assemblies [C++], creating
- conversions, C++ projects
- Visual C++ projects
ms.assetid: 4ef2cc1a-e3e5-4d67-8d8d-9c614f8ec5d3
ms.openlocfilehash: de3742717bf55c53ab4007aaed18b6ce687fbede
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817375"
---
# <a name="how-to-create-verifiable-c-projects-ccli"></a>Gewusst wie: Erstellen überprüfbarer C++-Projekte (C++ / CLI)

Visual C++-Anwendungs-Assistenten werden keine überprüfbaren Projekte erstellt.

> [!IMPORTANT]
> Visual Studio 2015 als veraltet markiert und Visual Studio 2017 nicht unterstützt. die **/CLR: pure** und **/CLR: safe** überprüfbare Projekte. Wenn Sie die überprüfbaren Code benötigen, empfehlen wir, dass Sie Ihren Code in C# übersetzen.

Allerdings bei Verwendung eine ältere Version von Visual C++-Compiler-Toolsets, die unterstützt **/CLR: pure** und **/CLR: safe**, Projekte konvertiert werden können, um überprüfbar zu sein. Dieses Thema beschreibt das Festlegen von Projekteigenschaften, und ändern die Quelldateien zum Transformieren von Visual C++-Projekten zum Erzeugen von überprüfbarer Anwendungen.

## <a name="compiler-and-linker-settings"></a>Compiler und Linker-Einstellungen

In der Standardeinstellung .NET-Projekte das Compilerflag "/ CLR" verwenden und konfigurieren den Linker an, auf der Zielhardware X86. Für überprüfbaren Code müssen Sie den/CLR: safe-Flag verwenden, und Sie müssen den Linker anweisen, anstatt systemeigene maschinenanweisungen MSIL generieren.

### <a name="to-change-the-compiler-and-linker-settings"></a>Zum Ändern der Einstellungen für Compiler und linker

1. Zeigen Sie die Eigenschaftenseite des Projekts. Weitere Informationen finden Sie unter [Compiler festgelegt und Buildeigenschaften](../build/working-with-project-properties.md).

1. Auf der **allgemeine** Seite die **Konfigurationseigenschaften** Knotengruppe, die **Common Language Runtime-Unterstützung** Eigenschaft **Sichere MSIL Common Language Runtime-Unterstützung (/ CLR: safe)**.

1. Auf der **erweitert** Seite die **Linker** Knotengruppe, die **CLR-Imagetyp** Eigenschaft **sicheres IL-Bild erzwingen (/ CLRIMAGETYPE: safe)**.

## <a name="removing-native-data-types"></a>Entfernen von systemeigenen Datentypen

Da die systemeigenen Datentypen nicht überprüfbar sind, auch wenn sie nicht tatsächlich verwendet werden, müssen Sie alle Header-Dateien, die mit systemeigenen Typen entfernen.

> [!NOTE]
> Das folgende Verfahren gilt für Windows Forms-Anwendung (.NET) und Console-Anwendung (.NET)-Projekte.

### <a name="to-remove-references-to-native-data-types"></a>So entfernen Sie Verweise auf die systemeigenen Datentypen

1. Kommentieren Sie den gesamten Inhalt der Datei "stdafx.h".

## <a name="configuring-an-entry-point"></a>Konfigurieren eines Einstiegspunktes

Da C-Laufzeitbibliotheken (CRT) nicht überprüfbare Anwendungen verwenden können, können nicht sie CRT aufrufen, die main-Funktion als Standardeinstiegspunkt abhängen. Dies bedeutet, dass Sie den Namen der Funktion, die anfänglich aufgerufen werden, an den Linker explizit angeben müssen. (In diesem Fall Main() anstelle von main() bzw. _tmain () verwendet, um einen nicht-CRT-Einstiegspunkt anzugeben, aber dieser Name ist frei wählbar, da der Einstiegspunkt explizit angegeben werden muss.)

> [!NOTE]
> Die folgenden Verfahren gelten für Konsole (.NET)-Projekte.

#### <a name="to-configure-an-entry-point"></a>So konfigurieren Sie einen Einstiegspunkt

1. Ändern Sie _tmain () in Main() im Haupt-cpp-Datei des Projekts an.

1. Zeigen Sie die Eigenschaftenseite des Projekts. Weitere Informationen finden Sie unter [Compiler festgelegt und Buildeigenschaften](../build/working-with-project-properties.md).

1. Auf der **erweitert** Seite die **Linker** Knoten geben Sie `Main` als die **Einstiegspunkt** -Eigenschaftswert.

## <a name="see-also"></a>Siehe auch

- [Reiner und überprüfbarer Code (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md)
