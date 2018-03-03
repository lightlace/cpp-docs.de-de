---
title: __getmainargs, __wgetmainargs | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __wgetmainargs
- __getmainargs
apilocation:
- msvcr100.dll
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
apitype: DLLExport
f1_keywords:
- __wgetmainargs
- __getmainargs
dev_langs:
- C++
helpviewer_keywords:
- __wgetmainargs
- __getmainargs
ms.assetid: f72f54eb-9509-4bdf-8752-40fc49055439
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 232f3eb49d2800ac43f2ef86d1a6f113afe9f67f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="getmainargs-wgetmainargs"></a>__getmainargs, __wgetmainargs
Ruft die Befehlszeilenanalyse auf und kopiert die Argumente für `main()` zurück durch die übergebenen Zeiger.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
int __getmainargs(  
    int * _Argc,   
   char *** _Argv,   
   char *** _Env,   
   int _DoWildCard,  
_startupinfo * _StartInfo);  
  
 int __wgetmainargs (  
   int *_Argc,  
   wchar_t ***_Argv,  
   wchar_t ***_Env,  
   int _DoWildCard,  
   _startupinfo * _StartInfo)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 `_Argc`  
 Eine Ganzzahl, die die Anzahl von Argumenten enthält, die in `argv` folgen. Der `argc`-Parameter ist immer größer als oder gleich 1.  
  
 `_Argv`  
 Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen. Gemäß Konvention ist `argv[0]` der Befehl, mit dem das Programm aufgerufen wird, argv[1] ist das erste Befehlszeilenargument, und so geht es weiter bis zu argv[argc], das immer NULL ist. Das erste Befehlszeilenargument ist immer `argv[1]`, und das letzte ist `argv[argc - 1]`.  
  
 `_Env`  
 Ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden. Das Array wird mit einem NULL-Eintrag beendet.  
  
 `_DoWildCard`  
 Eine ganze Zahl, die, wenn sie auf 1 festgelegt wird, die Platzhalter in den Befehlszeilenargumenten erweitert, oder keine Aktion ausführt, wenn sie auf 0 festgelegt wird.  
  
 `_StartInfo`  
 Andere Informationen, die an die CRT-DLL übergeben werden.  
  
## <a name="return-value"></a>Rückgabewert  
 0, wenn erfolgreich; ein negativer Wert, wenn fehlgeschlagen.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden Sie `__getmainargs` für nicht-Breitzeichen-Plattformen und `__wgetmainargs` für Breitzeichen (Unicode)-Plattformen.  
  
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|__getmainargs|internal.h|  
|__wgetmainargs|internal.h|