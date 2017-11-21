---
title: "Build-Anforderungen für Windows Vista-Standardsteuerelementen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- common controls (MFC), build requirements
- common controls (MFC)
ms.assetid: 025f7d55-55a2-4dcd-8f62-02424e3dcc04
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a6f6dabd14ddb95f1b4c2b49389c27f61a69970f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="build-requirements-for-windows-vista-common-controls"></a>Anforderungen für die Erstellung von Windows Vista-Standardsteuerelementen
Die Microsoft Foundation Class (MFC)-Bibliothek unterstützt allgemeine Windows-Steuerelemente, Version 6.1. Allgemeine Steuerelemente sind in enthalten [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] und in die Bibliothek enthalten die [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)]. Die Bibliothek stellt neue Methoden, die Verbesserung der vorhandenen Klassen und neue Klassen und Methoden, die unterstützen [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] allgemeine Steuerelemente. Wenn Sie eine Anwendung erstellen, sollten Sie die Kompilierung und die Migration Anforderungen befolgen, die in den folgenden Abschnitten beschrieben werden.  
  
## <a name="compilation-requirements"></a>Kompilierungsanforderungen  
  
### <a name="supported-versions"></a>Unterstützte Versionen  
 Einige neue Klassen und Methoden unterstützen nur [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] und höher, während andere Methoden auch früheren Betriebssystemen unterstützt. Ein Hinweis in der `Requirements` Abschnitt jedes Themas Methode gibt an, wenn die mindestens erforderliche Betriebssystem [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)].  
  
 Selbst wenn Ihr Computer nicht ausgeführt werden kann [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)], können Sie eine MFC-Anwendung, die ausgeführt werden, auf Erstellen [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] haben die Version 6.1 MFC-Headerdateien auf Ihrem Computer. Allerdings Standardsteuerelemente, die speziell für dienen [!INCLUDE[windowsver](../build/reference/includes/windowsver_md.md)] nur auf diesem System ausgeführt werden und werden von früheren Betriebssystemen ignoriert.  
  
### <a name="supported-character-sets"></a>Unterstützte Zeichensätze  
 Die neue Windows-Standardsteuerelemente unterstützen nur den Unicode-Zeichensatz und nicht ANSI-Zeichensatz. Wenn Sie Ihre Anwendung in der Befehlszeile erstellen, verwenden beide der folgenden Definition (/ D)-Zeichensatz Compileroptionen in Unicode als zugrunde liegenden angeben:  
  
```  
/D_UNICODE /DUNICODE  
```  
  
 Wenn Sie Ihre Anwendung in der integrierten Entwicklungsumgebung (IDE) von Visual Studio erstellen, geben Sie die **Unicode-Zeichensatz** -Option von der **Zeichensatz** Eigenschaft in der **Allgemein**  Knoten den Projekteigenschaften.  
  
 Die ANSI-Version von mehreren MFC-Methoden sind veraltet allgemeine Windows-Steuerelemente, Version 6.1 ab. Weitere Informationen finden Sie unter [ANSI-APIs veraltet](../mfc/deprecated-ansi-apis.md).  
  
## <a name="migration-requirements"></a>Migrationsanforderungen  
 Wenn Sie Visual Studio-IDE verwenden, um eine neue MFC-Anwendung zu erstellen, die allgemeine Windows-Steuerelemente, Version 6.1 verwendet, deklariert die IDE automatisch eine entsprechende Manifest. Jedoch wenn Sie eine vorhandene MFC-Anwendung von einer früheren Version von Visual Studio migrieren und die neuen Standardsteuerelemente verwenden möchten, bietet die IDE automatisch Manifestinformationen zum Aktualisieren der Anwendungsstatus keine. Stattdessen müssen Sie manuell den folgenden Quellcode in der Datei "stdafx.h" einfügen:  
  
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

