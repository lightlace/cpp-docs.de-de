---
title: ComPtr-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr
dev_langs:
- C++
helpviewer_keywords:
- ComPtr class
ms.assetid: a6551902-6819-478a-8df7-b6f312ab1fb0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1a20dd5e2fb43dd5caae7a5185260d8c88637d33
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597961"
---
# <a name="comptr-class"></a>ComPtr-Klasse

Erstellt einen *intelligenten Zeigertyp* , der die Schnittstelle darstellt, die vom Vorlagenparameter angegeben wird. **ComPtr** automatisch verwaltet einen Verweiszähler für den zugrunde liegenden Schnittstellenzeiger und gibt die Schnittstelle frei, wenn der Verweiszähler auf Null geht.

## <a name="syntax"></a>Syntax

```cpp
template <typename T>
class ComPtr;

template<class T>
friend class ComPtr;
```

### <a name="parameters"></a>Parameter

*T*  
Die Schnittstelle, die die **ComPtr** darstellt.

*U*  
Eine Klasse, die aktuelle **ComPtr** ist ein Friend. (Die Vorlage, die diesen Parameter verwendet, ist geschützt.)

## <a name="remarks"></a>Hinweise

`ComPtr<>` deklariert einen Typ, der den zugrunde liegenden Schnittstellenzeiger darstellt. Verwenden Sie `ComPtr<>` auf eine Variable deklarieren und verwenden Sie dann auf den Pfeil-Memberzugriffsoperator (`->`) auf eine Schnittstellenmemberfunktion zuzugreifen.

Weitere Informationen zu intelligenten Zeigern finden Sie unter der Unterabschnitt "Intelligente Zeiger für COM" den [COM Coding Practices](/windows/desktop/LearnWin32/com-coding-practices)in der MSDN Library.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`InterfaceType`|Ein Synonym für den vom angegebenen Typ der *T* Template-Parameter.|

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[ComPtr::ComPtr-Konstruktor](../windows/comptr-comptr-constructor.md)|Initialisiert eine neue Instanz der dem **ComPtr** Klasse. Überladungen stellen Standard-, Kopier-, Verschiebe- und Konvertierungskonstruktoren bereit.|
|[ComPtr::~ComPtr-Destruktor](../windows/comptr-tilde-comptr-destructor.md)|Hebt die Initialisierung einer Instanz von **ComPtr**.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ComPtr::As-Methode](../windows/comptr-as-method.md)|Gibt eine **ComPtr** -Objekt, das die Schnittstelle, die durch den angegebenen Vorlagenparameter gekennzeichnet darstellt.|
|[ComPtr::AsIID-Methode](../windows/comptr-asiid-method.md)|Gibt eine **ComPtr** Objekt, das die Schnittstelle, die die angegebene Schnittstellen-ID identifizierte darstellt.|
|[ComPtr::AsWeak-Methode](../windows/comptr-asweak-method.md)|Ruft einen schwachen Verweis (WeakReference) auf das aktuelle Objekt ab.|
|[ComPtr::Attach-Methode](../windows/comptr-attach-method.md)|Dies ordnet **ComPtr** mit dem Schnittstellentyp, der von der aktuellen Vorlagentyp-Parameter angegeben.|
|[ComPtr::CopyTo-Methode](../windows/comptr-copyto-method.md)|Kopiert die aktuelle oder angegebene-Schnittstelle, die zugeordneten **ComPtr** auf den angegebenen Ausgabezeiger.|
|[ComPtr::Detach-Methode](../windows/comptr-detach-method.md)|Hebt die Zuordnung dieser **ComPtr** von der Schnittstelle, die es darstellt.|
|[ComPtr::Get-Methode](../windows/comptr-get-method.md)|Ruft einen Zeiger auf die Schnittstelle, die mit dieser verknüpft ist **ComPtr**.|
|[ComPtr::GetAddressOf-Methode](../windows/comptr-getaddressof-method.md)|Ruft die Adresse der [Ptr_](../windows/comptr-ptr-data-member.md) Datenmember, der einen Zeiger auf die von dieser Schnittstelle enthält **ComPtr**.|
|[ComPtr::ReleaseAndGetAddressOf-Methode](../windows/comptr-releaseandgetaddressof-method.md)|Gibt die Schnittstelle frei zugeordneten **comptr-Objekt** und ruft dann die Adresse der [Ptr_](../windows/comptr-ptr-data-member.md) Datenmember, der einen Zeiger auf die Schnittstelle enthält, die veröffentlicht wurde.|
|[ComPtr::Reset](../windows/comptr-reset.md)|Gibt alle Verweise für den Zeiger auf die Schnittstelle, die mit dieser verknüpft ist **ComPtr**.|
|[ComPtr::Swap-Methode](../windows/comptr-swap-method.md)|Tauscht die Schnittstelle, die von der aktuellen verwalteten **ComPtr** mit der Schnittstelle, die durch das angegebene verwaltete **ComPtr**.|

### <a name="protected-methods"></a>Geschützte Methoden

|Name|Beschreibung|
|----------|-----------------|
|[ComPtr::InternalAddRef-Methode](../windows/comptr-internaladdref-method.md)|Inkrementiert den Verweiszähler der Schnittstelle zugeordneten **ComPtr**.|
|[ComPtr::InternalRelease-Methode](../windows/comptr-internalrelease-method.md)|Führt einen COM-Freigabe-Vorgang für die Schnittstelle zugeordneten **ComPtr**.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[ComPtr::operator Microsoft::WRL::Details::BoolType-Operator](../windows/comptr-operator-microsoft-wrl-details-booltype-operator.md)|Gibt an, ob eine **ComPtr** die Objektlebensdauer einer Schnittstelle verwaltet.|
|[ComPtr::operator&-Operator](../windows/comptr-operator-ampersand-operator.md)|Ruft die Adresse des aktuellen **ComPtr**.|
|[ComPtr::operator=-Operator](../windows/comptr-operator-assign-operator.md)|Weist einen Wert mit dem aktuellen **ComPtr**.|
|[ComPtr::operator->-Operator](../windows/comptr-operator-arrow-operator.md)|Ruft einen Zeiger auf den Typ ab, der durch den aktuellen Vorlagenparameter angegeben ist.|
|[ComPtr::operator==-Operator](../windows/comptr-operator-equality-operator.md)|Gibt an, ob zwei **ComPtr** Objekte gleich sind.|
|[ComPtr::operator!=-Operator](../windows/comptr-operator-inequality-operator.md)|Gibt an, ob zwei **ComPtr** -Objekte ungleich sind.|

### <a name="protected-data-members"></a>Geschützte Datenmember

|name|Beschreibung|
|----------|-----------------|
|[ComPtr::ptr_-Datenmember](../windows/comptr-ptr-data-member.md)|Enthält einen Zeiger auf die Schnittstelle, die zugeordnet wird, und das von diesem verwaltet **ComPtr**.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`ComPtr`

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)