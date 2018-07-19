---
title: Importieren in eine Anwendung mithilfe von "__declspec(dllimport)" "| Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- __declspec
- dllimport
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllimport) keyword [C++]
- importing DLLs [C++], __declspec(dllimport)
ms.assetid: edb4da4e-f83a-44cf-a668-9239d49dbe42
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82974ec688fbe688c98188c2e99a54462da81165
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32368833"
---
# <a name="importing-into-an-application-using-declspecdllimport"></a>Importieren in eine Anwendung mithilfe von "__declspec(dllimport)"
Wenn ein Programm öffentliche, durch eine DLL definierte Symbole verwendet, wird dieser Vorgang als Importieren bezeichnet. Beim Erstellen von Headerdateien für Anwendungen, die Erstellungsvorgang Ihre DLLs verwenden, verwenden **von "__declspec(dllimport)" "** für die Deklarationen der öffentlichen Symbole. Das Schlüsselwort **von "__declspec(dllimport)" "** funktioniert, ob Sie mit der DEF-Dateien oder Exportieren der **__declspec(dllexport)** Schlüsselwort.  
  
 Um den Code verständlicher zu gestalten, definieren Sie ein Makro für **von "__declspec(dllimport)" "** und klicken Sie dann das Makro verwenden, um die Deklaration aller importierten Symbole:  
  
```  
#define DllImport   __declspec( dllimport )  
  
DllImport int  j;  
DllImport void func();  
```  
  
 Mit **von "__declspec(dllimport)" "** ist bei Funktionsdeklarationen optional, aber der Compiler effizienter Code erzeugt, wenn Sie dieses Schlüsselwort verwenden. Sie müssen allerdings verwenden **von "__declspec(dllimport)" "** für die importierende ausführbare Datei, auf die öffentlichen Datensymbole und Objekte des DLL zugreifen. Beachten Sie, dass die Benutzer Ihrer DLL noch eine Verknüpfung mit einer Importbibliothek herstellen müssen.  
  
 Sie können dieselbe Headerdatei sowohl für die DLL als auch für die Clientanwendung nutzen. Verwenden Sie zu diesem Zweck ein spezielles Präprozessorsymbol, das angibt, ob die DLL oder die Clientanwendung erstellt wird. Zum Beispiel:  
  
```  
#ifdef _EXPORTING  
   #define CLASS_DECLSPEC    __declspec(dllexport)  
#else  
   #define CLASS_DECLSPEC    __declspec(dllimport)  
#endif  
  
class CLASS_DECLSPEC CExampleA : public CObject  
{ ... class definition ... };  
```  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Initialisieren einer DLL](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)