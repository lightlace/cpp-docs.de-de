---
title: 'Platform:: writeonlyarray-Klasse | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WriteOnlyArray::begin
- VCCORLIB/Platform::WriteOnlyArray::Data
- VCCORLIB/Platform::WriteOnlyArray::end
- VCCORLIB/Platform::WriteOnlyArray::FastPass
- VCCORLIB/Platform::WriteOnlyArray::Length
- VCCORLIB/Platform::WriteOnlyArray::set
dev_langs:
- C++
helpviewer_keywords:
- Platform::WriteOnlyArray Class
ms.assetid: 92d7dd56-ec58-4b8c-88ba-9c903668b687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44beeca9b860e2010b092739d8c39044ad0bb5b1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43680924"
---
# <a name="platformwriteonlyarray-class"></a>Platform::WriteOnlyArray-Klasse
Stellt ein eindimensionales Array dar, das als Eingabeparameter verwendet wird, wenn der Aufrufer ein Array für die zu füllende Methode übergibt.  
  
 Diese Verweisklasse wird als privat in vccorlib.h deklariert. Daher wird sie nicht in Metadaten ausgegeben und kann nur von C++ verwendet werden. Diese Klasse ist nur zur Verwendung als Eingabeparameter vorgesehen, der ein Array empfängt, das der Aufrufer zugeordnet hat. Sie ist nicht vom Benutzercode konstruierbar. Sie ermöglicht es einer C++-Methode, direkt in dieses Array zu schreiben – ein Muster, das als *FillArray* -Muster bezeichnet wird. Weitere Informationen finden Sie unter [Array und WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
private ref class WriteOnlyArray<T, 1>  
```  
  
### <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
 Diese Methoden verfügen über interne Zugreifbarkeit, das heißt, sie sind nur innerhalb der C++-App oder -Komponente zugänglich.  
  
|name|Beschreibung|  
|----------|-----------------|  

|[Writeonlyarray:: Begin](#begin)| Ein Iterator, der auf das erste Element des Arrays zeigt. |  
|[Writeonlyarray:: Data](#data)| Ein Zeiger auf den Datenpuffer. |  
|[Writeonlyarray:: End](#end)| Ein Iterator, der auf eine Stelle hinter dem letzten Element im Array zeigt. |  
|[Writeonlyarray:: Fastpass](#fastpass)| Gibt an, ob das Array den FastPass-Mechanismus verwendet werden kann, der eine Optimierung, die transparent vom System ausgeführt wird. Verwenden Sie dies nicht in Ihrem Code |  
|[Writeonlyarray:: length](#length)| Gibt die Anzahl der Elemente des Arrays zurück. |  
|[Writeonlyarray:: Set](#set)| Das angegebene Element auf den angegebenen Wert festgelegt. |  

  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 `WriteOnlyArray`  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
 **Metadaten:** platform.winmd  
  
 **Namespace:** Platform  

## <a name="begin"></a>  WriteOnlyArray::begin-Methode
Gibt einen Zeiger auf das erste Element im Array zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
T* begin() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erste Element im Array.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Iterator kann mit STL-Algorithmen wie `std::sort` verwendet werden, um Vorgänge auf Elemente im Array auszuführen.  
  


## <a name="data"></a>  WriteOnlyArray::Data-Eigenschaft
Zeiger auf den Datenpuffer.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property T* Data{  
   T* get() const;  
}  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf unformatierte Arraybytes.  
  


## <a name="end"></a>  WriteOnlyArray::end-Methode
Gibt einen Zeiger auf einen Punkt hinter dem letzten Element im Array zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
T* end() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeigeriterator auf einen Punkt hinter dem letzten Element im Array.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Iterator kann mit STL-Algorithmen verwendet werden, um Vorgänge wie `std::sort` auf die Array-Elemente auszuführen.  
  


## <a name="fastpass"></a>  WriteOnlyArray::FastPass-Eigenschaft
Gibt an, ob die interne FastPass-Optimierung ausgeführt werden kann. Ist nicht für die Verwendung in Benutzercode bestimmt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property bool FastPass{  
   bool get() const;  
}  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Boolescher Wert, der angibt, ob das Array FastPass ist.  
  


## <a name="get"></a>  Writeonlyarray:: Get-Methode
Gibt das Element am angegebenen Index zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
T& get(  
   unsigned int indexArg) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `indexArg`  
  
### <a name="return-value"></a>Rückgabewert  
  


## <a name="length"></a>  WriteOnlyArray::Length-Eigenschaft
Gibt die Anzahl der Elemente im vom Aufrufer reservierten Array zurück.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
property unsigned int Length{  
   unsigned int get() const;  
}  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente im Array.  
  


## <a name="set"></a>  WriteOnlyArray::set-Funktion
Legt den angegebenen Wert am angegebenen Index im Array fest.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
### <a name="parameters"></a>Parameter  
 `indexArg`  
 Der Index des festzulegenden Elements.  
  
 `valueArg`  
 Der bei `indexArg` festzulegende Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf das Element, das gerade festgelegt wurde.  
  

  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Interpretation des HRESULT-Werts finden Sie unter [Struktur von COM-Fehlercodes](/windows/desktop/com/structure-of-com-error-codes).  
  
  
## <a name="see-also"></a>Siehe auch  
 [Plattform-Namespace](platform-namespace-c-cx.md)   
 [Erstellen von Windows-Runtime-Komponenten in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)