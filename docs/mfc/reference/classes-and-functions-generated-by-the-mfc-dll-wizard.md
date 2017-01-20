---
title: "Vom MFC-DLL-Assistenten erstellte Klassen und Funktionen"
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
  - "Klassen [C++], Generiert vom MFC-DLL-Assistenten"
  - "Code [C++], Generiert vom MFC-DLL-Assistenten"
  - "DLLs [C++], Assistentenklassen und -funktionen"
  - "Funktionen [MFC]"
  - "Funktionen [MFC], DLLs"
  - "MFC-DLL-Assistent"
ms.assetid: e69e62fe-4953-42bf-a2fc-50bbf9bdaeaf
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Vom MFC-DLL-Assistenten erstellte Klassen und Funktionen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der vom MFC\-DLL\-Assistenten generierte Code hängt von der Art der erstellten DLL sowie von den ausgewählten Optionen ab.  Der MFC\-DLL\-Assistent generiert für beide Varianten regulärer DLLs denselben Code.  
  
|DLL\-Typ|Option|Klassen|Funktionen|  
|--------------|------------|-------------|----------------|  
|[Erweiterung](../../build/extension-dlls-overview.md)|Kein|Kein|`DllMain`|  
|[Regulär](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Kein|Von `CWinApp` abgeleitete Anwendungsklasse|Kein|  
|[Regulär](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Automatisierung|Von `CWinApp` abgeleitete Anwendungsklasse|**DllGetClassObjectDllCanUnloadNowDllRegisterServer**|  
|[Erweiterung](../../build/extension-dlls-overview.md)|Windows\-Sockets|Kein|`DllMain`|  
|[Regulär](../../build/regular-dlls-dynamically-linked-to-mfc.md)|Windows\-Sockets|Von `CWinApp` abgeleitete Anwendungsklasse|`InitInstance` enthält Aufruf an `AfxSocketInit`|  
  
## Siehe auch  
 [MFC\-DLL\-Assistent](../../mfc/reference/mfc-dll-wizard.md)