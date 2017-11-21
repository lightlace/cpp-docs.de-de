---
title: Exportieren aus einer DLL mithilfe von __declspec(dllexport) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- dllexport
- __declspec
dev_langs: C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 967b3a737893ac6f891ab6fbbc73de08b1084d67
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>Exportieren aus einer DLL mithilfe von "__declspec(dllexport)"
Microsoft eingeführt **__export** in 16-Bit-Compilerversion von Visual C++, damit der Compiler die Exportnamen automatisch generieren, und legen diese in einer LIB-Datei. Diese LIB-Datei kann dann wie eine statische LIB-Datei zur Verknüpfung mit einer DLL verwendet werden.  
  
 In neueren Compilerversionen können Sie Daten, Funktionen, Klassen oder Memberfunktionen von Klassen exportieren, aus einer DLL mithilfe der **__declspec(dllexport)** Schlüsselwort. **__declspec(dllexport)** der Objektdatei die Export-Anweisung hinzugefügt, daher Sie keine DEF-Datei müssen.  
  
 Am deutlichsten zeigt sich diese einfache Handhabung beim Exportieren von ergänzten C++-Funktionsnamen. Da es keine Standardspezifikation für die Namensergänzung gibt, kann der Name einer exportierten Funktion zwischen den einzelnen Compilerversionen variieren. Bei Verwendung von **__declspec(dllexport)**, Neukompilierung der DLL und die abhängigen .exe-Dateien ist nur für das Konto für alle naming Convention-Änderungen erforderlich.  
  
 Viele Exportanweisungen, z. B. Ordinalzahlen, NONAME und PRIVATE, können nur in einer DEF-Datei angegeben werden, und es gibt keine Möglichkeit, diese Attribute ohne DEF-Datei festzulegen. Allerdings **__declspec(dllexport)** zusätzlich zu einer DEF Datei bewirkt keinen Buildfehler.  
  
 Zum Exportieren von Funktionen der **__declspec(dllexport)** Schlüsselwort muss auf der linken Seite des Schlüsselworts für die Aufrufkonvention angezeigt, wenn ein Schlüsselwort angegeben wird. Zum Beispiel:  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 Um alle öffentlichen Datenmember und Memberfunktionen einer Klasse zu exportieren, muss das Schlüsselwort, wie im nachfolgenden Beispiel dargestellt, links vom Klassennamen erscheinen:  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)` kann nicht mit der `__clrcall`-Aufrufkonvention für eine Funktion übernommen werden.  
  
 Beim Erstellen der DLL erstellen Sie in der Regel eine Headerdatei mit den Funktionsprototypen oder Klassen, die Sie exportieren und hinzufügen **__declspec(dllexport)** den Deklarationen in der Headerdatei. Um den Code verständlicher zu gestalten, definieren Sie ein Makro für **__declspec(dllexport)** und verwenden Sie das Makro für jedes Symbol, das Sie exportieren:  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **__declspec(dllexport)** speichert Funktionsnamen in der Exporttabelle der DLL. Wenn Sie die Größe der Tabelle zu optimieren möchten, finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
> [!NOTE]
>  Wenn Sie DLL-Quellcode von Win16 auf Win32 portieren, ersetzen Sie jede Instanz des **__export** mit **__declspec(dllexport)**.  
  
 Zu Referenzzwecken können Sie die Win32-Headerdatei Winbase.h durchsuchen. Sie enthält Verwendungsbeispiele für **von "__declspec(dllimport)" "** Verwendung.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Exportieren Sie aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren Sie und importieren Sie mithilfe von AFX_EXT_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C++-Funktionen zur Verwendung in ausführbaren c-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C-Funktionen zur Verwendung in ausführbaren C oder C++-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Welche Exportmethode ermitteln](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren Sie in eine Anwendung mithilfe von "__declspec(dllimport)" "](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [__Declspec-Schlüsselwort](../cpp/declspec.md)  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)