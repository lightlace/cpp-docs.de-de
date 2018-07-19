---
title: Aufrufkonventionen, Parameter und Rückgabetyp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.assetid: 0ffa4558-6005-4803-be95-7a8ec8837660
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5680e4616a2af46066175928216022211bcb288f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372200"
---
# <a name="calling-conventions-parameters-and-return-type"></a>Aufrufkonventionen, Parameter und Rückgabetyp
Die Hilfsroutine hat den folgenden Prototyp:  
  
```  
FARPROC WINAPI __delayLoadHelper2(   
   PCImgDelayDescr pidd,  
   FARPROC * ppfnIATEntry  
);  
```  
  
 Dabei gilt:  
  
 `pidd`  
 Ein `const`-Zeiger zu `ImgDelayDescr` (siehe delayimp.h), der die Offsets verschiedener importrelevanter Daten, einen Zeitstempel für das Binden von Informationen und einen Satz von Attributen enthält, die weitere Informationen zum Inhalt des Deskriptors bereitstellen. Derzeit gibt es nur ein Attribut, `dlattrRva`, das angibt, dass die Adressen im Deskriptor relative virtuelle Adressen sind (im Gegensatz zu virtuellen Adressen).  
  
 Für die Definition der `PCImgDelayDescr` -Struktur, finden Sie unter [Struktur- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md).  
  
 `ppfnIATEntry`  
 Ein Zeiger zum Slot in der mit Verzögerung geladenen Importadresstabelle (IAT), die mit der Adresse der importierten Funktion aktualisiert werden soll. Die Hilfsroutine muss denselben Wert speichern, den sie an diesen Speicherort zurückgibt.  
  
## <a name="expected-return-values"></a>Erwartete Rückgabewerte  
 Wenn die Funktion erfolgreich ist, gibt sie die Adresse der importierten Funktion zurück.  
  
 Wenn die Funktion fehlschlägt, wird eine Ausnahme ausgelöst und 0 zurückgegeben. Es können drei Ausnahmetypen ausgelöst werden:  
  
-   Ein ungültiger Parameter, was passiert, wenn die Attribute in `pidd` nicht korrekt angegeben werden.  
  
-   `LoadLibrary` ist in der angegebenen DLL fehlgeschlagen.  
  
-   Fehlschlagen von `GetProcAddress`.  
  
 Es liegt in Ihrer Verantwortung, diese Ausnahmen zu handhaben.  
  
## <a name="remarks"></a>Hinweise  
 Die Aufrufkonvention für die Hilfsfunktion ist `__stdcall`. Der Typ des Rückgabewerts ist nicht relevant, deshalb wird FARPROC verwendet. Diese Funktion hat eine C-Bindung.  
  
 Der Rückgabewert für die Hilfsfunktion für das verzögerte Laden muss im übergegebenen Funktionszeigerspeicherort gespeichert werden, es sei denn, Sie möchten, dass Ihre Hilfsfunktion als Benachrichtigungshook verwendet wird. In diesem Fall ist Ihr Code dafür verantwortlich, den entsprechenden Funktionszeiger zum Zurückgeben zu finden. Der vom Linker generierte Thunkcode übernimmt dann diesen Rückgabewert als reales Ziel für den Importvorgang und springt direkt dorthin.  
  
## <a name="sample"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie eine einfache Hookfunktion implementieren.  
  
```  
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)  
{  
    switch (dliNotify) {  
        case dliStartProcessing :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return a pointer to a FARPROC helper function  
            // that will be used instead, thereby bypassing the rest   
            // of the helper.  
  
            break;  
  
        case dliNotePreLoadLibrary :  
  
            // If you want to return control to the helper, return 0.  
            // Otherwise, return your own HMODULE to be used by the   
            // helper instead of having it call LoadLibrary itself.  
  
            break;  
  
        case dliNotePreGetProcAddress :  
  
            // If you want to return control to the helper, return 0.  
            // If you choose you may supply your own FARPROC function   
            // address and bypass the helper's call to GetProcAddress.  
  
            break;  
  
        case dliFailLoadLib :   
  
            // LoadLibrary failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_MOD_NOT_FOUND) and exit.  
            // If you want to handle the failure by loading an alternate   
            // DLL (for example), then return the HMODULE for   
            // the alternate DLL. The helper will continue execution with   
            // this alternate DLL and attempt to find the  
            // requested entrypoint via GetProcAddress.  
  
            break;  
  
        case dliFailGetProc :  
  
            // GetProcAddress failed.  
            // If you don't want to handle this failure yourself, return 0.  
            // In this case the helper will raise an exception   
            // (ERROR_PROC_NOT_FOUND) and exit.  
            // If you choose you may handle the failure by returning   
            // an alternate FARPROC function address.  
  
            break;  
  
        case dliNoteEndProcessing :   
  
            // This notification is called after all processing is done.   
            // There is no opportunity for modifying the helper's behavior  
            // at this point except by longjmp()/throw()/RaiseException.   
            // No return value is processed.  
  
            break;  
  
        default :  
  
            return NULL;  
    }  
  
    return NULL;  
}  
  
/*   
and then at global scope somewhere  
PfnDliHook __pfnDliNotifyHook2 = delayHook;  
*/  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Die Hilfsfunktion](../../build/reference/understanding-the-helper-function.md)