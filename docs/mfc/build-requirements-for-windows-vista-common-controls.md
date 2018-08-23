---
title: Erstellen von Anforderungen für Windows Vista-Standardsteuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8d3e5c8cd6b4a0876d0cac8e1fb3c7e87eed9cc
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42539079"
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Anforderungen für die Erstellung von Windows Vista-Standardsteuerelementen
Die Microsoft Foundation Class (MFC)-Bibliothek unterstützt die Windows-Standardsteuerelemente, Version 6.1. Die allgemeinen Steuerelemente sind in Windows Vista enthalten, und die Bibliothek ist in Visual Studio SDK enthalten. Die Bibliothek bietet neue Methoden, die Verbesserung vorhandener Klassen, und neue Klassen und Methoden, die Windows Vista-Standardsteuerelementen zu unterstützen. Wenn Sie Ihre Anwendung erstellen, sollten Sie die Kompilierung und die Migration Anforderungen befolgen, die in den folgenden Abschnitten beschrieben werden.  
  
## <a name="compilation-requirements"></a>Kompilierungsanforderungen  
  
### <a name="supported-versions"></a>Unterstützte Versionen  
 Einige neue Klassen und Methoden unterstützen nur Windows Vista und später zwar andere Methoden unterstützen auch ältere Betriebssysteme. Hinweis in der `Requirements` Abschnitt jedes Themas Methode gibt an, wenn die mindestens erforderliche Betriebssystem ist Windows Vista.  
  
 Auch wenn Ihr Computer nicht mit Windows Vista ausgeführt wird, können Sie eine MFC-Anwendung erstellen, die unter Windows Vista ausgeführt werden, wenn Sie die Version 6.1 MFC-Headerdateien auf Ihrem Computer verfügen. Allerdings allgemeine Steuerelemente, die speziell für Windows Vista dienen nur auf dem System ausgeführt werden und werden von älteren Betriebssystemen ignoriert.  
  
### <a name="supported-character-sets"></a>Unterstützte Zeichensätze  
 Die neuen Windows-Standardsteuerelemente unterstützen nur die Unicode-Zeichensatz und nicht ANSI-Zeichensatz. Wenn Sie Ihre Anwendung in der Befehlszeile erstellen, verwenden Sie beide der folgenden Definition (/ D) Compileroptionen an Unicode als den zugrunde liegenden Zeichensatz:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Wenn Sie Ihre Anwendung in der integrierten Entwicklungsumgebung (IDE) von Visual Studio erstellen, geben Sie die **Unicode-Zeichensatz** Möglichkeit, die **Character Set,** -Eigenschaft in der **Allgemein**  Knoten der Projekteigenschaften.  
  
 Die ANSI-Version von mehreren MFC-Methoden sind veraltet, beginnend mit Windows-Standardsteuerelemente, Version 6.1. Weitere Informationen finden Sie unter [ANSI-APIs als veraltet markiert](../mfc/deprecated-ansi-apis.md).  
  
## <a name="migration-requirements"></a>Migrationsanforderungen  
 Wenn Sie Visual Studio-IDE verwenden, um eine MFC-Anwendung zu erstellen, die allgemeine Windows-Steuerelemente, Version 6.1 verwendet, wird die IDE automatisch eine entsprechende Manifest deklariert. Jedoch wenn Sie eine vorhandene MFC-Anwendung von einer früheren Version von Visual Studio migrieren und die neuen Standardsteuerelemente verwenden möchten, bietet die IDE automatisch Informationen zum Aktualisieren Ihrer Anwendung aus dem Assemblymanifest keine. Stattdessen müssen Sie manuell in den folgenden Quellcode einfügen Ihrer **"stdafx.h"** Datei:  
  
```  
#ifdef UNICODE  
#if defined _M_IX86  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='x86' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_IA64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='ia64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#elif defined _M_X64  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='amd64' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#else  
#pragma comment(linker,"/manifestdependency:\"type='win32' name='Microsoft.Windows.Common-Controls' version='6.0.0.0' processorArchitecture='*' publicKeyToken='6595b64144ccf1df' language='*'\"")  
#endif  
#endif  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [Hierarchiediagramm](../mfc/hierarchy-chart.md)   
 [Veraltete ANSI-APIs](../mfc/deprecated-ansi-apis.md)

