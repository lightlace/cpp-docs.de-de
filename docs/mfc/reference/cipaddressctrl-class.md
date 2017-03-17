---
title: Klasse CIPAddressCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CIPAddressCtrl
- AFXCMN/CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::CIPAddressCtrl
- AFXCMN/CIPAddressCtrl::ClearAddress
- AFXCMN/CIPAddressCtrl::Create
- AFXCMN/CIPAddressCtrl::CreateEx
- AFXCMN/CIPAddressCtrl::GetAddress
- AFXCMN/CIPAddressCtrl::IsBlank
- AFXCMN/CIPAddressCtrl::SetAddress
- AFXCMN/CIPAddressCtrl::SetFieldFocus
- AFXCMN/CIPAddressCtrl::SetFieldRange
dev_langs:
- C++
helpviewer_keywords:
- IP address control
- Internet address edit box
- CIPAddressCtrl class
- Internet protocol address box
- common controls, Internet Explorer 4.0
- Internet Explorer 4.0 common controls
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b3849580c7bfd07f241e55cc48144959566d7d09
ms.lasthandoff: 02/24/2017

---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Steuerelements für IP-Adressen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Erstellt ein `CIPAddressCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Löscht den Inhalt des Steuerelements für IP-Adressen.|  
|[CIPAddressCtrl::Create](#create)|Erstellt ein IP-Adressensteuerelement und fügt es ein `CIPAddressCtrl` Objekt.|  
|[CIPAddressCtrl::CreateEx](#createex)|Erstellt eine IP-Adresse-Steuerelement mit dem angegebenen erweiterten Fensterstile und fügt es ein `CIPAddressCtrl` Objekt.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|Ruft die Werte für alle vier Felder im IP-Adresse-Steuerelement ab.|  
|[CIPAddressCtrl::IsBlank](#isblank)|Bestimmt, ob alle Felder in der IP-Adressensteuerelement leer sind.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Legt die Werte für alle vier Felder in die IP-Adressensteuerelement fest.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Legt den Tastaturfokus auf das angegebene Feld in die IP-Adressensteuerelement.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Legt den Bereich im angegebenen Feld in der IP-Adressensteuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Steuerelement für IP-Adresse, eine-Steuerelement ein Bearbeitungssteuerelement, können Sie eingeben und bearbeiten eine numerische Adresse Internetprotokoll (IP)-Format.  
  
 Dieses Steuerelement (und somit die `CIPAddressCtrl` Klasse) steht nur für Programme, die unter Microsoft Internet Explorer 4.0 und höher ausgeführt. Es werden auch unter zukünftigen Versionen von Windows und Windows NT verfügbar sein.  
  
 Weitere allgemeine Informationen zu den IP-Adressensteuerelement, finden Sie unter [IP-Adresse Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb761372) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CIPAddressCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmn.h  
  
##  <a name="cipaddressctrl"></a>CIPAddressCtrl::CIPAddressCtrl  
 Erstellt ein `CIPAddressCtrl`-Objekt.  
  
```  
CIPAddressCtrl();
```  
  
##  <a name="clearaddress"></a>CIPAddressCtrl::ClearAddress  
 Löscht den Inhalt des Steuerelements für IP-Adressen.  
  
```  
void ClearAddress();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="create"></a>CIPAddressCtrl::Create  
 Erstellt ein IP-Adressensteuerelement und fügt es ein `CIPAddressCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Format der IP-Adresse-Steuerelements. Eine Kombination von Window-Stile anwenden Sie umfasst die **WS_CHILD** formatieren, da das Steuerelement ein untergeordnetes Fenster sein muss. Finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste der Windows-Formate.  
  
 `rect`  
 Ein Verweis auf die IP-Adresse des Steuerelements Größe und Position. Es kann entweder eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder ein [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Ein Zeiger auf die IP-Adresse des Steuerelements übergeordnetes Fenster. Er darf nicht sein **NULL.**  
  
 `nID`  
 Die IP-Adresse des Steuerelements-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen ein `CIPAddressCtrl` Objekt in zwei Schritten.  
  
1.  Rufen Sie den Konstruktor, der erstellt die `CIPAddressCtrl` Objekt.  
  
2.  Rufen Sie **erstellen**, der die IP-Adressensteuerelement erstellt.  
  
 Wenn Sie erweiterte Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="createex"></a>CIPAddressCtrl::CreateEx  
 Rufen Sie diese Funktion zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CIPAddressCtrl` Objekt.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwExStyle`  
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Format der IP-Adresse-Steuerelements. Eine Kombination von Window-Stile anwenden Sie umfasst die **WS_CHILD** formatieren, da das Steuerelement ein untergeordnetes Fenster sein muss. Finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für eine Liste der Windows-Formate.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) -Struktur, die die Größe und Position des Fensters erstellt werden, in Clientkoordinaten des beschreibt `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das übergeordnete Element des Steuerelements ist.  
  
 `nID`  
 Der ID des Steuerelements untergeordnete Fenster  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) erweiterten Fensterstile, angegeben durch den Wert der Windows-erweiterten Stil anwenden **WS_EX_**.  
  
##  <a name="getaddress"></a>CIPAddressCtrl::GetAddress  
 Ruft die Werte für alle vier Felder im IP-Adresse-Steuerelement ab.  
  
```  
int GetAddress(
    BYTE& nField0,  
    BYTE& nField1,  
    BYTE& nField2,  
    BYTE& nField3);  
  
int GetAddress(DWORD& dwAddress);
```  
  
### <a name="parameters"></a>Parameter  
 `nField0`  
 Ein Verweis auf den Wert des Felds 0 durch eine gepackte IP-Adresse.  
  
 `nField1`  
 Ein Verweis auf den Feldwert 1 durch eine gepackte IP-Adresse.  
  
 `nField2`  
 Ein Verweis auf den Feldwert 2 durch eine gepackte IP-Adresse.  
  
 `nField3`  
 Ein Verweis auf den Feldwert 3 durch eine gepackte IP-Adresse.  
  
 `dwAddress`  
 Ein Verweis auf die Adresse einer `DWORD` -Wert, der die IP-Adresse empfängt. Finden Sie unter **Hinweise** für eine Tabelle, die zeigt, wie `dwAddress` gefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der nicht leeren Feldern in der IP-Adressensteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Der erste Prototyp die Werte in Feldern 0 bis 3 des Steuerelements Lesen von links nach rechts bzw., füllen die vier Parameter. Im zweiten oben Prototyp `dwAddress` wird folgendermaßen aufgefüllt.  
  
|Feld|Der Wert des Felds mit Bits|  
|-----------|-------------------------------------|  
|0|24 bis 31|  
|1|16 bis 23|  
|2|8 bis 15|  
|3|0 bis 7|  
  
##  <a name="isblank"></a>CIPAddressCtrl::IsBlank  
 Bestimmt, ob alle Felder in der IP-Adressensteuerelement leer sind.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn alle IP-Adressensteuerelement Felder leer sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setaddress"></a>CIPAddressCtrl::SetAddress  
 Legt die Werte für alle vier Felder in die IP-Adressensteuerelement fest.  
  
```  
void SetAddress(
    BYTE nField0,  
    BYTE nField1,  
    BYTE nField2,  
    BYTE nField3);  
  
void SetAddress(DWORD dwAddress);
```  
  
### <a name="parameters"></a>Parameter  
 `nField0`  
 Der Wert des Felds 0 durch eine gepackte IP-Adresse.  
  
 `nField1`  
 Der Wert des Felds 1 durch eine gepackte IP-Adresse.  
  
 `nField2`  
 Der Wert des Felds 2 durch eine gepackte IP-Adresse.  
  
 `nField3`  
 Der Wert des Felds 3 durch eine gepackte IP-Adresse.  
  
 `dwAddress`  
 Ein `DWORD` Wert, der die neue IP-Adresse enthält. Finden Sie unter **Hinweise** für eine Tabelle, die zeigt, wie die `DWORD` Wert gefüllt wird.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Der erste Prototyp die Werte in Feldern 0 bis 3 des Steuerelements Lesen von links nach rechts bzw., füllen die vier Parameter. Im zweiten oben Prototyp `dwAddress` wird folgendermaßen aufgefüllt.  
  
|Feld|Der Wert des Felds mit Bits|  
|-----------|-------------------------------------|  
|0|24 bis 31|  
|1|16 bis 23|  
|2|8 bis 15|  
|3|0 bis 7|  
  
##  <a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus  
 Legt den Tastaturfokus auf das angegebene Feld in die IP-Adressensteuerelement.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Parameter  
 `nField`  
 Nullbasierte Feldindex auf das der Fokus festgelegt werden soll. Ist dieser Wert größer als die Anzahl der Felder, wird der Fokus auf das erste leere Feld gesetzt. Wenn alle Felder nicht leer sind, wird der Fokus auf das erste Feld gesetzt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="setfieldrange"></a>CIPAddressCtrl::SetFieldRange  
 Legt den Bereich im angegebenen Feld in der IP-Adressensteuerelement fest.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>Parameter  
 `nField`  
 Nullbasierte Feldindex auf die Bereich angewendet werden soll.  
  
 `nLower`  
 Ein Verweis auf eine ganze Zahl, die die Untergrenze des angegebenen Felds in dieser IP-Adressensteuerelement empfangen.  
  
 `nUpper`  
 Ein Verweis auf eine ganze Zahl, die die Obergrenze des angegebenen Felds in dieser IP-Adressensteuerelement empfangen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Verwenden Sie die zwei Parameter, `nLower` und `nUpper`, um anzugeben, die oberen und unteren Grenzwerten des Felds, anstatt die *wRange* die Win32-Meldung als Parameter.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




