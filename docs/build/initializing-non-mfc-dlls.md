---
title: "Initialisieren MFC-fremder DLLs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], nicht-MFC"
  - "Initialisieren von DLLs"
  - "Nicht-MFC-DLLs [C++]"
ms.assetid: 2622b32a-28f9-4d61-9e46-6c19aaf8b7ad
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Initialisieren MFC-fremder DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Um MFC\-fremde DLLs zu initialisieren, muss der DLL\-Quellcode eine Funktion mit dem Namen `DllMain` enthalten.  Der folgende Code stellt ein grundlegendes Gerüst dar, das veranschaulicht, wie die Definition von `DllMain` aussehen könnte:  
  
```  
BOOL APIENTRY DllMain(HANDLE hModule,   
                      DWORD  ul_reason_for_call,   
                      LPVOID lpReserved)  
{  
    switch( ul_reason_for_call ) {  
    case DLL_PROCESS_ATTACH:  
    ...  
    case DLL_THREAD_ATTACH:  
    ...  
    case DLL_THREAD_DETACH:  
    ...  
    case DLL_PROCESS_DETACH:  
    ...  
    }  
    return TRUE;  
}  
```  
  
> [!NOTE]
>  Laut [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)]\-Dokumentation für **DllEntryPoint** muss der tatsächliche Name der Einstiegspunktfunktion mit der \/ENTRY\-Option in der Linkerbefehlszeile angegeben werden.  In Visual C\+\+ brauchen Sie die **\/ENTRY**\-Option jedoch nicht zu verwenden, wenn der Name der Einstiegspunktfunktion `DllMain` lautet.  Vielmehr wird die C\-Laufzeitbibliothek nicht ordnungsgemäß initialisiert, wenn Sie die **\/ENTRY**\-Option verwenden und die Einstiegspunktfunktion nicht den Namen **Dllmain** aufweist.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [\<caps:sentence id\="tgt7" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>Die Funktionsspezifikation für DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic Link Library\-Einstiegspunktfunktion \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
-   [Das Verhalten der C\-Laufzeitbibliothek und \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
## Siehe auch  
 [Initialisieren einer DLL](../build/initializing-a-dll.md)