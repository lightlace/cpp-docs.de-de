---
title: _set_app_type | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_app_type
apilocation: api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_app_type
- corecrt_startup/_set_app_type
dev_langs: C++
ms.assetid: 1e7fe786-b587-4116-8c05-f7d762350100
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: adfd7344b01360df6af3ccf7a153eda3451d2482
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="setapptype"></a>_set_app_type
Eine beim Start verwendete interne Funktion, die die CRT mitteilen soll, ob die App eine Konsolen-App oder eine GUI-Anwendung ist.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
typedef enum _crt_app_type
{
    _crt_unknown_app,
    _crt_console_app,
    _crt_gui_app
} _crt_app_type;

void __cdecl _set_app_type(
    _crt_app_type appType
    ); 
```  
  
## <a name="parameters"></a>Parameter  
 `appType`  
 Ein Wert, der den Anwendungstyp angibt. Mögliche Werte sind:  
  
|Wert|description|  
|----------------|-----------------|  
|_crt_unknown_app|Unbekannter Anwendungstyp.|  
|_crt_console_app|(Befehlszeilen)-Konsolenanwendung.|  
|_crt_gui_app|GUI-(Windows)-Anwendung.|  
  
## <a name="remarks"></a>Hinweise  
 In der Regel müssen Sie diese Funktion nicht aufrufen. Sie ist Teil des C-Laufzeitstartcodes, der ausgeführt wird, bevor `main` in Ihrer Anwendung aufgerufen wird.
 
## <a name="requirements"></a>Anforderungen  
  
|-Routine zurückgegebener Wert|Erforderlicher Header|  
|-------------|---------------------|  
|_set_app_type|process.h|

