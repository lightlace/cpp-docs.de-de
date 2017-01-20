---
title: "Konvertieren von Projekten im gemischten Modus in reine Intermediate Language"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Intermediate Language, Anwendungen im gemischten Modus"
  - "Anwendungen im gemischten Modus"
  - "Anwendungen im gemischten Modus, Intermediate Language"
  - "Projekte [C++], Konvertieren in Intermediate Language"
ms.assetid: 855f9e3c-4f09-4bfe-8eab-a45f68292be9
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Konvertieren von Projekten im gemischten Modus in reine Intermediate Language
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Alle CLR\-Projekte von Visual C\+\+ sind in der Standardeinstellung mit C\-Laufzeitbibliotheken verknüpft.  Folglich werden diese Projekte als Anwendungen im gemischten Modus klassifiziert, da in ihnen systemeigener Code mit Code kombiniert ist, der die Common Language Runtime \(verwalteten Code\) einbindet.  Sie werden ggf. in Intermediate Language \(IL\) kompiliert, die auch als Microsoft Intermediate Language \(MSIL\) bekannt ist.  
  
### So konvertieren Sie eine Anwendung im gemischten Modus in reine Intermediate Language  
  
1.  Entfernen Sie Links zu den [C\-Laufzeitbibliotheken](../c-runtime-library/crt-library-features.md) \(CRT\):  
  
    1.  Ändern Sie in der CPP\-Datei, durch die der Einstiegspunkt der Anwendung definiert wird, den Einstiegspunkt in `Main()`.  Die Verwendung von `Main()` weist darauf hin, dass das Projekt nicht mit CRT verknüpft wird.  
  
    2.  Klicken Sie in Projektmappen\-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie im Kontextmenü **Eigenschaften**, um die Eigenschaftenseiten für die Anwendung zu öffnen.  
  
    3.  Wählen Sie auf der Projekteigenschaftenseite **Erweitert** für den **Linker** das Feld **Einstiegspunkt** aus, und geben Sie dann in dieses Feld **Main** ein.  
  
    4.  Bei Konsolenanwendungen wählen Sie auf der Projekteigenschaftenseite **System** für den **Linker** das Feld **SubSystem** aus und ändern es in **Konsole \(\/SUBSYSTEM:CONSOLE\)**.  
  
        > [!NOTE]
        >  Diese Eigenschaft muss für Windows Forms\-Anwendungen nicht festgelegt werden, da das Feld **SubSystem** standardmäßig auf **Windows \(\/SUBSYSTEM:WINDOWS\)** festgelegt ist.  
  
    5.  Kommentieren Sie in stdafx.h alle `#include`\-Anweisungen aus.  Beispielsweise in Konsolenanwendungen:  
  
        ```  
        // #include <iostream>  
        // #include <tchar.h>  
        ```  
  
         \- oder \-  
  
         in Windows Forms\-Anwendungen:  
  
        ```  
        // #include <stdlib.h>  
        // #include <malloc.h>  
        // #include <memory.h>  
        // #include <tchar.h>  
        ```  
  
    6.  Bei Windows Forms\-Anwendungen kommentieren Sie in "Form1.cpp" die `#include`\-Anweisung aus, die auf "windows.h" verweist.  Beispiel:  
  
        ```  
        // #include <windows.h>  
        ```  
  
2.  Fügen Sie zu stdafx.h den folgenden Code hinzu:  
  
    ```  
    #ifndef __FLTUSED__  
    #define __FLTUSED__  
       extern "C" __declspec(selectany) int _fltused=1;  
    #endif  
    ```  
  
3.  Entfernen Sie alle nicht verwalteten Typen:  
  
    1.  Ersetzen Sie nicht verwaltete Typen, sofern angebracht, durch Verweise auf Strukturen aus dem [System](https://msdn.microsoft.com/en-us/library/system.appdomainmanager.appdomainmanager.aspx)\-Namespace.  Gebräuchliche verwaltete Typen sind in der folgenden Tabelle aufgeführt:  
  
        |Struktur|**Beschreibung**|  
        |--------------|----------------------|  
        |[\<caps:sentence id\="tgt24" sentenceid\="84e2c64f38f78ba3ea5c905ab5a2da27" class\="tgtSentence"\>Boolean\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.boolean\(v=vs.140\).aspx)|Stellt einen booleschen Wert dar.|  
        |[\<caps:sentence id\="tgt26" sentenceid\="40ea57d3ee3c07bf1c102b466e1c3091" class\="tgtSentence"\>Byte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte\(v=vs.140\).aspx)|Stellt eine 8\-Bit\-Ganzzahl ohne Vorzeichen dar.|  
        |[\<caps:sentence id\="tgt28" sentenceid\="a87deb01c5f539e6bda34829c8ef2368" class\="tgtSentence"\>Char\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.char\(v=vs.140\).aspx)|Stellt ein Unicode\-Zeichen dar.|  
        |[\<caps:sentence id\="tgt30" sentenceid\="dfeaaeb4316477bd556ea5e8c3295887" class\="tgtSentence"\>DateTime\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.datetime.datetime.aspx)|Stellt einen Zeitpunkt dar, der normalerweise durch Datum und Uhrzeit dargestellt wird.|  
        |[\<caps:sentence id\="tgt32" sentenceid\="bdaa3c20a3e3851599514f7c6be5f62f" class\="tgtSentence"\>Decimal\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.decimal\(v=vs.140\).aspx)|Stellt eine Dezimalzahl dar.|  
        |[\<caps:sentence id\="tgt34" sentenceid\="e8cd7da078a86726031ad64f35f5a6c0" class\="tgtSentence"\>Double\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.double\(v=vs.140\).aspx)|Stellt eine Gleitkommazahl mit doppelter Genauigkeit dar.|  
        |[\<caps:sentence id\="tgt36" sentenceid\="1e0ca5b1252f1f6b1e0ac91be7e7219e" class\="tgtSentence"\>Guid\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.guid\(v=vs.140\).aspx)|Stellt eine GUID dar \(Globally Unique Identifier, globaler eindeutiger Bezeichner\).|  
        |[\<caps:sentence id\="tgt38" sentenceid\="ce80d5ec65b1d2a2f1049eadc100db23" class\="tgtSentence"\>Int16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int16\(v=vs.140\).aspx)|Stellt eine 16\-Bit\-Ganzzahl mit Vorzeichen dar.|  
        |[\<caps:sentence id\="tgt40" sentenceid\="0241adbbd83925f051b694d40f02747f" class\="tgtSentence"\>Int32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int32\(v=vs.140\).aspx)|Stellt eine 32\-Bit\-Ganzzahl mit Vorzeichen dar.|  
        |[\<caps:sentence id\="tgt42" sentenceid\="ff9b3f96d37353c528517bc3656a00a8" class\="tgtSentence"\>Int64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.int64\(v=vs.140\).aspx)|Stellt eine 64\-Bit\-Ganzzahl mit Vorzeichen dar.|  
        |[\<caps:sentence id\="tgt44" sentenceid\="7f1db863563907cf33604ed7fad6b111" class\="tgtSentence"\>IntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.intptr\(v=vs.140\).aspx)|Ein plattformabhängiger Typ zur Darstellung von Zeigern und Handles.|  
        |[\<caps:sentence id\="tgt46" sentenceid\="943756eb7841efcc43b7cd37d7254c76" class\="tgtSentence"\>SByte\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.byte.aspx)|Stellt eine ganze 8\-Bit\-Zahl mit Vorzeichen dar.|  
        |[\<caps:sentence id\="tgt48" sentenceid\="dd5c07036f2975ff4bce568b6511d3bc" class\="tgtSentence"\>Single\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.single.aspx)|Stellt eine Gleitkommazahl mit einfacher Genauigkeit dar.|  
        |[\<caps:sentence id\="tgt50" sentenceid\="90150402997ea9c8dc45cc4d41bb28cb" class\="tgtSentence"\>TimeSpan\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.timespan\(v=vs.140\).aspx)|Stellt ein Zeitintervall dar.|  
        |[\<caps:sentence id\="tgt52" sentenceid\="a00ef2ef85ff67b7b39339886f19044f" class\="tgtSentence"\>UInt16\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint16\(v=vs.140\).aspx)|Stellt eine vorzeichenlose 16\-Bit\-Ganzzahl dar.|  
        |[\<caps:sentence id\="tgt54" sentenceid\="3de84ad0700f2a1571f633d399e1900e" class\="tgtSentence"\>UInt32\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint32\(v=vs.140\).aspx)|Stellt eine vorzeichenlose 32\-Bit\-Ganzzahl dar.|  
        |[\<caps:sentence id\="tgt56" sentenceid\="2e8d31865e5d4b9d8611e1b991baed07" class\="tgtSentence"\>UInt64\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uint64\(v=vs.140\).aspx)|Stellt eine vorzeichenlose 64\-Bit\-Ganzzahl dar.|  
        |[\<caps:sentence id\="tgt58" sentenceid\="92d74abda31865424016b16e2c806a66" class\="tgtSentence"\>UIntPtr\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.uintptr\(v=vs.140\).aspx)|Ein plattformabhängiger Typ zur Darstellung von Zeigern und Handles.|  
        |[\<caps:sentence id\="tgt60" sentenceid\="cab8111fd0b710a336c898e539090e34" class\="tgtSentence"\>Void\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.void\(v=vs.140\).aspx)|Zeigt eine Methode an, die keinen Wert zurückgibt, d. h. eine Methode mit dem Rückgabetyp "void".|