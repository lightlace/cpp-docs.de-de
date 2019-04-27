---
title: Konvertieren von Projekten im gemischten Modus in reine Intermediate Language
ms.date: 11/04/2016
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
ms.openlocfilehash: 93eff646fb582e25ad70549afc714c5321e56079
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209242"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Konvertieren von Projekten im gemischten Modus in reine intermediate language

Alle Visual C++-CLR-Projekte werden standardmäßig auf die C-Laufzeitbibliotheken verknüpfen. Daher werden diese Projekte als Anwendungen im gemischten Modus, klassifiziert werden, weil sie systemeigenen Code mit Code kombinieren, die die common Language Runtime (verwalteter Code). Wenn sie kompiliert werden, werden sie in der Zwischensprache (IL), auch bekannt als Microsoft intermediate Language (MSIL) kompiliert.

> [!IMPORTANT]
> Visual Studio 2015 als veraltet markiert und Visual Studio 2017 nicht mehr unterstützt die Erstellung von **/CLR: pure** oder **/CLR: safe** Code für die CLR-Anwendungen. Wenn Sie rein oder sicher-Assemblys benötigen, empfehlen wir, dass Sie Ihre Anwendung in c# übersetzen.

Bei Verwendung eine frühere Version von Visual C++-Compiler-Toolsets, die unterstützt **/CLR: pure** oder **/CLR: safe**, Sie können dieses Verfahren verwenden, um Ihren Code in reine MSIL zu konvertieren:

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Konvertieren Sie Ihre Anwendung im gemischten Modus in reine intermediate language

1. Entfernen Sie Links zu den [C-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md) (CRT):

   1. In der CPP-Datei definiert den Einstiegspunkt der Anwendung, ändern Sie den Einstiegspunkt für `Main()`. Mithilfe von `Main()` gibt an, dass das Projekt nicht mit der CRT verknüpft ist.

   2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste in des Projekts, und wählen **Eigenschaften** im Kontextmenü, um die Eigenschaftenseiten für Ihre Anwendung zu öffnen.

   3. In der **erweitert** Eigenschaftenseite des Projekts für die **Linker**, wählen die **Einstiegspunkt** und geben Sie dann **Main** in diesem Feld.

   4. Für konsolenanwendungen in der **System** Eigenschaftenseite des Projekts für die **Linker**, wählen die **SubSystem** Feld, und ändern Sie diese Option, um **Konsole (/ Subsystem:Console)**.

      > [!NOTE]
      > Sie müssen nicht dieser Eigenschaft für Windows Forms-Anwendungen festlegen, da die **SubSystem** Feld nastaven NA hodnotu **Windows (/ SUBSYSTEM: WINDOWS)** standardmäßig.

   5. Kommentieren Sie in "stdafx.h", alle der `#include` Anweisungen. Z. B. in konsolenanwendungen:

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       - oder - 

       Z. B. in Windows Forms-Anwendungen:

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Für Windows Forms-Anwendungen in Form1.cpp, Auskommentieren der `#include` -Anweisung, windows.h verweist. Zum Beispiel:

      ```cpp
      // #include <windows.h>
      ```

2. Fügen Sie auf "stdafx.h" den folgenden Code hinzu:

   ```cpp
   #ifndef __FLTUSED__
   #define __FLTUSED__
      extern "C" __declspec(selectany) int _fltused=1;
   #endif
   ```

3. Entfernen Sie alle nicht verwaltete Typen an:

   Ersetzen Sie sofern angebracht, die nicht verwaltete Typen mit Verweisen auf Strukturen aus der [System](/dotnet/api/system) Namespace. Allgemeine verwaltete Typen sind in der folgenden Tabelle aufgeführt:

   |Struktur|Beschreibung|
   |---------------|-----------------|
   |[Boolean](/dotnet/api/system.boolean)|Stellt einen booleschen Wert dar.|
   |[Byte](/dotnet/api/system.byte)|Stellt eine ganze 8-Bit-Zahl ohne Vorzeichen dar.|
   |[Char](/dotnet/api/system.char)|Stellt ein Unicode-Zeichen dar.|
   |[DateTime](/dotnet/api/system.datetime)|Stellt einen Zeitpunkt dar, der normalerweise durch Datum und Uhrzeit dargestellt wird.|
   |[Decimal](/dotnet/api/system.decimal)|Stellt eine Dezimalzahl dar.|
   |[Double](/dotnet/api/system.double)|Stellt eine Gleitkommazahl mit doppelter Genauigkeit dar.|
   |[Guid](/dotnet/api/system.guid)|Stellt eine GUID dar (Globally Unique Identifier, globaler eindeutiger Bezeichner).|
   |[Int16](/dotnet/api/system.int16)|Stellt eine 16-Bit-Ganzzahl mit Vorzeichen dar.|
   |[Int32](/dotnet/api/system.int32)|Stellt eine 32-Bit-Ganzzahl mit Vorzeichen dar.|
   |[Int64](/dotnet/api/system.int64)|Stellt eine 64-Bit-Ganzzahl mit Vorzeichen dar.|
   |[IntPtr](/dotnet/api/system.intptr)|Ein plattformabhängiger Typ zur Darstellung von Zeigern und Handles.|
   |[SByte](/dotnet/api/system.byte)|Stellt eine ganze 8-Bit-Zahl mit Vorzeichen dar.|
   |[Single](/dotnet/api/system.single)|Stellt eine Gleitkommazahl mit einfacher Genauigkeit dar.|
   |[TimeSpan](/dotnet/api/system.timespan)|Stellt ein Zeitintervall dar.|
   |[UInt16](/dotnet/api/system.uint16)|Stellt eine vorzeichenlose 16-Bit-Ganzzahl dar.|
   |[UInt32](/dotnet/api/system.uint32)|Stellt eine vorzeichenlose 32-Bit-Ganzzahl dar.|
   |[UInt64](/dotnet/api/system.uint64)|Stellt eine vorzeichenlose 64-Bit-Ganzzahl dar.|
   |[UIntPtr](/dotnet/api/system.uintptr)|Ein plattformabhängiger Typ zur Darstellung von Zeigern und Handles.|
   |[Void](/dotnet/api/system.void)|Zeigt eine Methode, die keinen Wert zurückgibt. Das heißt, hat die Methode der void-Rückgabetyp.|