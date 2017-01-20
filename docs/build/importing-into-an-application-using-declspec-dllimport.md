---
title: "Importieren in eine Anwendung mithilfe von &quot;__declspec(dllimport)&quot;"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport)-Schlüsselwort [C++]"
  - "Importieren von DLLs [C++], __declspec(dllimport)"
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Importieren in eine Anwendung mithilfe von &quot;__declspec(dllimport)&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn ein Programm öffentliche, durch eine DLL definierte Symbole verwendet, wird dieser Vorgang als Importieren bezeichnet.  Wenn Sie Headerdateien für Anwendungen erstellen, die für den Erstellungsvorgang Ihre DLLs verwenden, sollten Sie für die Deklarationen der öffentlichen Symbole **\_\_declspec\(dllimport\)** verwenden.  Das **\_\_declspec\(dllimport\)**\-Schlüsselwort funktioniert unabhängig davon, ob der Export über DEF\-Dateien oder über das **\_\_declspec\(dllexport\)**\-Schlüsselwort erfolgt.  
  
 Um den Code lesbarer zu gestalten, definieren Sie ein Makro für **\_\_declspec\(dllimport\)** und verwenden dieses Makro zur Deklaration aller importierten Symbole:  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 Die Verwendung von **\_\_declspec\(dllimport\)** ist bei Funktionsdeklarationen optional, der Compiler generiert jedoch effizienteren Code, wenn Sie dieses Schlüsselwort verwenden.  **\_\_declspec\(dllimport\)** muss jedoch verwendet werden, damit die importierende ausführbare Datei auf die öffentlichen Datensymbole und Objekte der DLL zugreifen kann.  Beachten Sie, dass die Benutzer Ihrer DLL noch eine Verknüpfung mit einer Importbibliothek herstellen müssen.  
  
 Sie können dieselbe Headerdatei sowohl für die DLL als auch für die Clientanwendung nutzen.  Verwenden Sie zu diesem Zweck ein spezielles Präprozessorsymbol, das angibt, ob die DLL oder die Clientanwendung erstellt wird.  Beispiel:  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## Was möchten Sie tun?  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)