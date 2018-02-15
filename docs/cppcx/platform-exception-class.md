---
title: 'Platform:: Exception-Klasse | Microsoft Docs'
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Exception::Exception
- VCCORLIB/Platform::Exception::CreateException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
dev_langs:
- C++
helpviewer_keywords:
- Platform::Exception Class
ms.assetid: ca1d5a67-3a5a-48fe-8099-f9c38a2d2dce
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51df721524fa871b28cc7e4bcb088d4a82a0d1ad
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="platformexception-class"></a>Platform::Exception-Klasse
Stellt Fehler dar, die beim Ausführen einer Anwendung auftreten. Benutzerdefinierte Ausnahmeklassen können nicht von `Platform::Exception`abgeleitet werden. Wenn Sie eine benutzerdefinierte Ausnahme benötigen, können Sie `Platform::COMException` verwenden und ein app-spezifisches HRESULT angeben.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
public ref class Exception : Object,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="members"></a>Member  
 Die `Exception` -Klasse erbt von der `Object` -Klasse und den Schnittstellen `IException`, `IPrintable`und `IEquatable` .  
  
 Die `Exception` -Klasse verfügt auch über die folgenden Arten von Membern.  
  
### <a name="constructors"></a>Konstruktoren  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[Exception::Exception](#ctor)|Initialisiert eine neue Instanz der `Exception`-Klasse.|  
  
### <a name="methods"></a>Methoden  
 Die `Exception` -Klasse erbt die Methoden `Equals()`, `Finalize()`,`GetHashCode()`,`GetType()`,`MemberwiseClose()`und `ToString()` von [Platform::Object Class](../cppcx/platform-object-class.md)abgeleitet werden. Die `Exception` -Klasse verfügt auch über die folgende Methode.  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[Exception::CreateException](#createexception)|Erstellt eine Ausnahme, die den angegebenen HRESULT-Wert darstellt.|  
  
### <a name="properties"></a>Eigenschaften  
 Die Ausnahmeklasse verfügt auch über die folgenden Eigenschaften:  
  
|Member|Beschreibung|  
|------------|-----------------|  
|[Exception::HResult](#hresult)|Das HRESULT, das der Ausnahme entspricht.|  
|[Exception::Message](#message)|Eine Meldung, in der die Ausnahme beschrieben wird. Dieser Wert ist schreibgeschützt und kann nicht geändert werden, nachdem `Exception` erstellt wurde.|  
  
### <a name="requirements"></a>Anforderungen  
 **Unterstützter Client:** Windows 8  
  
 **Unterstützter Server:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Metadaten:** platform.winmd  

## <a name="createexception"></a> Exception:: createexception-Methode
Erstellt ein Platform::Exception^ aus einem angegebenen HRESULT-Wert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
Exception^ CreateException(int32 hr)  
Exception^ CreateException(int32 hr, Platform::String^ message)  
```  
  
### <a name="parameters"></a>Parameter  
 hr  
 Ein HRESULT-Wert, den Sie in der Regel aus einem Aufruf an eine COM-Methode erhalten. Wenn der Wert 0, was identisch mit S_OK ist ist, löst diese Methode [Platform:: InvalidArgumentException](../cppcx/platform-invalidargumentexception-class.md) da COM-Methoden keine Ausnahmen auslösen sollen.  
  
 message  
 Eine Zeichenfolge, die den Fehler beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Ausnahme, die den Fehler HRESULT darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Ausnahme aus einem HRESULT zu erstellen, die beispielsweise aus einem Aufruf einer COM-Schnittstellen-Methode zurückgegeben wird. Sie können die Überladung verwenden, die einen String^-Parameter erhält, um eine benutzerdefinierte Meldung bereitzustellen.  
  
 Es wird dringend empfohlen, createexception zu verwenden, um eine stark typisierte Ausnahme zu erstellen und keine [Platform:: COMException](../cppcx/platform-comexception-class.md) , die lediglich HRESULT enthält.  
  


## <a name="ctor"></a>  Exception:: Exception-Konstruktor
Initialisiert eine neue Instanz der Exception-Klasse.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
  
Exception(int32 hresult)  
Exception(int32 hresult, ::Platform::String^ message)  
```  
  
### <a name="parameters"></a>Parameter  
 `hresult`  
 Der Fehler HRESULT, der durch die Ausnahme repräsentiert wird.  
  
 `message`  
 Eine vom Benutzer angegebene Meldung, beispielsweise vorschreibender Text, der der Ausnahme zugeordnet ist. Im Allgemeinen sollten Sie die zweite Überladung verwenden, um eine beschreibende Meldung bereitzustellen, die möglichst spezifisch erläutert, wie und warum der Fehler aufgetreten ist.  
  


## <a name="hresult"></a>  Exception:: HRESULT-Eigenschaft
Das HRESULT, das der Ausnahme entspricht.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## <a name="property-value"></a>Eigenschaftswert  
 Der HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die meisten Ausnahmen fangen als COM-Fehler an, die als HRESULT-Werte zurückgegeben werden. C++/CX konvertiert diese Werte in Platform::Exception^-Objekte, und diese Eigenschaft speichert den Wert des ursprünglichen Fehlercodes.  
  


## <a name="message"></a> Exception:: Message-Eigenschaft
Die Meldung, in der der Fehler beschrieben wird.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
public:property String^ Message;  
```  
  
## <a name="property-value"></a>Eigenschaftswert  
 In den Ausnahmen, die aus der Windows Runtime stammen, ist dieses eine vom System bereitgestellte Beschreibung des Fehlers.  
  
### <a name="remarks"></a>Hinweise  
 In Windows 8 ist diese Eigenschaft schreibgeschützt, da Ausnahmen in dieser Version von Windows-Runtime über die ABI nur als HRESULTS transportiert werden. Bei Windows 8.1 werden umfangreichere Ausnahmeinformationen über die ABI transportiert, und Sie können eine benutzerdefinierte Meldung bereitstellen, auf die andere Komponenten programmgesteuert zugreifen können. Weitere Informationen finden Sie unter [Ausnahmen (C + c++ / CX)](../cppcx/exceptions-c-cx.md).  
  

  
## <a name="see-also"></a>Siehe auch  
 [Plattformnamespace](../cppcx/platform-namespace-c-cx.md)