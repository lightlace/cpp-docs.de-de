---
title: "Exception::CreateException-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::CreateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::CreateException-Methode"
ms.assetid: 70e72bb4-3fec-478d-af3d-9ec8762d2825
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::CreateException-Methode
Erstellt ein Platform::Exception^ aus einem angegebenen HRESULT\-Wert.  
  
## Syntax  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
## Parameter  
 hr  
 Ein HRESULT\-Wert, den Sie in der Regel aus einem Aufruf an eine COM\-Methode erhalten. Wenn der Wert 0 ist, was identisch mit S\_OK ist, löst diese Methode [Platform::InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) aus, da nachfolgende COM\-Methoden keine Ausnahmen auslösen sollen.  
  
 message  
 Eine Zeichenfolge, die den Fehler beschreibt.  
  
## Rückgabewert  
 Eine Ausnahme, die den Fehler HRESULT darstellt.  
  
## Hinweise  
 Verwenden Sie diese Methode, um eine Ausnahme aus einem HRESULT zu erstellen, die beispielsweise aus einem Aufruf einer COM\-Schnittstellen\-Methode zurückgegeben wird. Sie können die Überladung verwenden, die einen String^\-Parameter erhält, um eine benutzerdefinierte Meldung bereitzustellen.  
  
 Es wird dringend empfohlen, CreateException zu verwenden, um eine stark typisierte Ausnahme anstelle einer [Platform::COMException](../cppcx/platform-comexception-class.md) zu erstellen, die lediglich HRESULT enthält.  
  
## Anforderungen  
 **Unterstützter Client \(Mindestversion\):** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Unterstützter Server \(Mindestversion\):** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  
  
## Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)