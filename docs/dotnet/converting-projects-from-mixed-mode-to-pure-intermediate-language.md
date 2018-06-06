---
title: Konvertieren von Projekten aus gemischten Modus in reine Intermediate Language | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- intermediate language, mixed-mode applications
- mixed-mode applications
- mixed-mode applications, intermediate language
- projects [C++], converting to intermediate language
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 98560841b40b7bb4691222dfa254f06a071b07da
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704632"
---
# <a name="converting-projects-from-mixed-mode-to-pure-intermediate-language"></a>Konvertieren von Projekten im gemischten Modus in reine intermediate language

Alle Visual C++-CLR-Projekte werden standardmäßig auf die C-Laufzeitbibliotheken verknüpfen. Daher werden diese Projekte als Anwendungen im gemischten Modus, klassifiziert, da sie nativen Code mit Code kombinieren, die die common Language Runtime (verwalteter Code) ausgerichtet ist. Wenn sie kompiliert werden, werden sie in intermediate Language (IL), auch bekannt als Microsoft intermediate Language (MSIL) kompiliert.

> [!IMPORTANT]
> Visual Studio 2015 als veraltet markiert und 2017 von Visual Studio nicht mehr unterstützt die Erstellung von **/CLR: pure** oder **/CLR: safe** Code für CLR-Anwendungen. Wenn Sie die reinen oder sicheren Assemblys benötigen, empfehlen wir, dass Sie Ihre Anwendung in c# übersetzen.

Wenn Sie eine frühere Version von Visual C++-Compilertoolset verwenden, die unterstützt **/CLR: pure** oder **/CLR: safe**, verwenden Sie dieses Verfahren, um den Code in reine MSIL zu konvertieren:

### <a name="to-convert-your-mixed-mode-application-into-pure-intermediate-language"></a>Konvertieren Sie Ihre Anwendung im gemischten Modus in reine intermediate language

1. Entfernen Sie Links zu den [C-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md) (CRT):

   1. In der CPP-Datei definieren den Einstiegspunkt der Anwendung, ändern Sie den Einstiegspunkt für `Main()`. Mithilfe von `Main()` gibt an, dass das Projekt nicht mit der CRT verknüpft ist.

   2. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste des Projekts, und wählen **Eigenschaften** im Kontextmenü auf die Eigenschaftenseiten für Ihre Anwendung zu öffnen.

   3. In der **erweitert** Projekteigenschaftenseite für die **Linker**, wählen die **Einstiegspunkt** und geben Sie dann **Main** in diesem Feld.

   4. Für konsolenanwendungen in der **System** Projekteigenschaftenseite für die **Linker**, wählen die **SubSystem** Feld und ändern Sie diese Option, um **Konsole (/ Subsystem:Console)**.

      > [!NOTE]
      > Sie müssen nicht dieser Eigenschaft für Windows Forms-Anwendungen festlegen, da der **SubSystem** Feld **Windows (/ SUBSYSTEM: WINDOWS)** standardmäßig.

   5. Kommentieren Sie in "stdafx.h", dann alle den `#include` Anweisungen. Beispielsweise ist in konsolenanwendungen:

      ```cpp
      // #include <iostream>
      // #include <tchar.h>
      ```

       - oder - 

       Beispielsweise ist in Windows Forms-Anwendungen:

      ```cpp
      // #include <stdlib.h>
      // #include <malloc.h>
      // #include <memory.h>
      // #include <tchar.h>
      ```

   6. Für Windows Forms-Anwendungen in Form1.cpp, kommentieren Sie die `#include` -Anweisung, windows.h verweist. Zum Beispiel:

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

3. Entfernen Sie alle nicht verwalteten Typen an:

   Gegebenenfalls ersetzen Sie nicht verwaltete Typen mit Verweisen auf Strukturen aus dem [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx) Namespace. Allgemeine verwaltete Typen sind in der folgenden Tabelle aufgeführt:

   |Struktur|Beschreibung|
   |---------------|-----------------|
   |[Boolean](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Stellt einen booleschen Wert dar.|
   |[Byte](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Stellt eine ganze 8-Bit-Zahl ohne Vorzeichen dar.|
   |[Char](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Stellt ein Unicode-Zeichen dar.|
   |[DateTime](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Stellt einen Zeitpunkt dar, der normalerweise durch Datum und Uhrzeit dargestellt wird.|
   |[Decimal](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Stellt eine Dezimalzahl dar.|
   |[Double](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Stellt eine Gleitkommazahl mit doppelter Genauigkeit dar.|
   |[Guid](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Stellt eine GUID dar (Globally Unique Identifier, globaler eindeutiger Bezeichner).|
   |[Int16](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Stellt eine 16-Bit-Ganzzahl mit Vorzeichen dar.|
   |[Int32](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Stellt eine 32-Bit-Ganzzahl mit Vorzeichen dar.|
   |[Int64](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Stellt eine 64-Bit-Ganzzahl mit Vorzeichen dar.|
   |[IntPtr](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Ein plattformabhängiger Typ zur Darstellung von Zeigern und Handles.|
   |[SByte](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Stellt eine ganze 8-Bit-Zahl mit Vorzeichen dar.|
   |[Single](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Stellt eine Gleitkommazahl mit einfacher Genauigkeit dar.|
   |[TimeSpan](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Stellt ein Zeitintervall dar.|
   |[UInt16](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Stellt eine vorzeichenlose 16-Bit-Ganzzahl dar.|
   |[UInt32](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Stellt eine vorzeichenlose 32-Bit-Ganzzahl dar.|
   |[UInt64](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Stellt eine vorzeichenlose 64-Bit-Ganzzahl dar.|
   |[UIntPtr](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Ein plattformabhängiger Typ zur Darstellung von Zeigern und Handles.|
   |["void"](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Zeigt eine Methode, die keinen Wert zurückgibt. d. h. verfügt über die Methode der void-Rückgabetyp.|