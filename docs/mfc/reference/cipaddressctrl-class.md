---
title: CIPAddressCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CIPAddressCtrl [MFC], CIPAddressCtrl
- CIPAddressCtrl [MFC], ClearAddress
- CIPAddressCtrl [MFC], Create
- CIPAddressCtrl [MFC], CreateEx
- CIPAddressCtrl [MFC], GetAddress
- CIPAddressCtrl [MFC], IsBlank
- CIPAddressCtrl [MFC], SetAddress
- CIPAddressCtrl [MFC], SetFieldFocus
- CIPAddressCtrl [MFC], SetFieldRange
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67c775f314cc70da1b662ca9b9c5f0a2e68eb2bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cipaddressctrl-class"></a>CIPAddressCtrl-Klasse
Stellt die Funktionalität des allgemeinen Windows-Steuerelements für IP-Adressen bereit.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CIPAddressCtrl::CIPAddressCtrl](#cipaddressctrl)|Erstellt ein `CIPAddressCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CIPAddressCtrl::ClearAddress](#clearaddress)|Löscht den Inhalt des Steuerelements für IP-Adressen.|  
|[CIPAddressCtrl::Create](#create)|Erstellt eine IP-Adressensteuerelement und fügt es einer `CIPAddressCtrl` Objekt.|  
|[CIPAddressCtrl::CreateEx](#createex)|Erstellt ein Steuerelement für die IP-Adresse mit der angegebenen erweiterten Fensterstile und fügt es einer `CIPAddressCtrl` Objekt.|  
|[CIPAddressCtrl::GetAddress](#getaddress)|Ruft die Adresswerte für alle vier Felder in die IP-Adressensteuerelement ab.|  
|[CIPAddressCtrl::IsBlank](#isblank)|Bestimmt, ob alle Felder in die IP-Adressensteuerelement leer sind.|  
|[CIPAddressCtrl::SetAddress](#setaddress)|Legt die Werte für alle vier Felder in die IP-Adressensteuerelement fest.|  
|[CIPAddressCtrl::SetFieldFocus](#setfieldfocus)|Legt den Tastaturfokus auf das angegebene Feld in die IP-Adressensteuerelement fest.|  
|[CIPAddressCtrl::SetFieldRange](#setfieldrange)|Legt den Bereich im angegebenen Feld in die IP-Adressensteuerelement fest.|  
  
## <a name="remarks"></a>Hinweise  
 Ein IP-Adresse-Steuerelement ein Steuerelement mit einem Bearbeitungssteuerelement vergleichbar können Sie eine numerische Adresse im Format Internetprotokoll (IP) zu geben.  
  
 Dieses Steuerelement (und somit die `CIPAddressCtrl` Klasse) steht nur für Programme, die unter Microsoft Internet Explorer 4.0 und höher ausgeführt. Sie werden auch unter zukünftigen Versionen von Windows und Windows NT verfügbar sein.  
  
 Weitere allgemeine Informationen über die IP-Adresse finden Sie unter [IP-Adresse Steuerelemente](http://msdn.microsoft.com/library/windows/desktop/bb761372) im Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_CLEARADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761377)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="create"></a>CIPAddressCtrl::Create  
 Erstellt eine IP-Adressensteuerelement und fügt es einer `CIPAddressCtrl` Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `dwStyle`  
 Die IP-Adressensteuerelement-Stil. Wenden Sie eine Kombination von Fensterstile. Müssen Sie auch die **WS_CHILD** formatieren, da das Steuerelement ein untergeordnetes Fenster sein muss. Finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in das Windows SDK für eine Liste der Windows-Formate.  
  
 `rect`  
 Ein Verweis auf die IP-Adressensteuerelement Größe und Position. Es kann es sich um eine [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt oder eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur.  
  
 `pParentWnd`  
 Ein Zeiger auf die IP-Adressensteuerelement des übergeordneten Fensters. Es muss nicht **NULL.**  
  
 `nID`  
 Die IP-Adressensteuerelement-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Initialisierung erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie erstellen eine `CIPAddressCtrl` Objekt in zwei Schritten.  
  
1.  Rufen Sie den Konstruktor erstellt die `CIPAddressCtrl` Objekt.  
  
2.  Rufen Sie **erstellen**, wodurch die IP-Adressensteuerelement erstellt.  
  
 Wenn Sie die erweiterten Fensterstile mit dem Steuerelement verwenden möchten, rufen Sie [CreateEx](#createex) anstelle von **erstellen**.  
  
##  <a name="createex"></a>CIPAddressCtrl::CreateEx  
 Mit dieser Funktion wird zum Erstellen eines Steuerelements (ein untergeordnetes Fenster), und ordnen sie die `CIPAddressCtrl` Objekt.  
  
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
 Gibt den erweiterten Stil des Steuerelements erstellt wird. Eine Liste der erweiterten Fensterstile, finden Sie unter der `dwExStyle` -Parameter für [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) im Windows SDK.  
  
 `dwStyle`  
 Die IP-Adressensteuerelement-Stil. Wenden Sie eine Kombination von Fensterstile. Müssen Sie auch die **WS_CHILD** formatieren, da das Steuerelement ein untergeordnetes Fenster sein muss. Finden Sie unter [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) in das Windows SDK für eine Liste der Windows-Formate.  
  
 `rect`  
 Ein Verweis auf eine [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) Struktur, die beschreibt, die Größe und Position des Fensters erstellt werden, in Clientkoordinaten der `pParentWnd`.  
  
 `pParentWnd`  
 Ein Zeiger auf das Fenster, das das Steuerelement übergeordnet ist.  
  
 `nID`  
 Das Steuerelement untergeordnete Fenster-ID.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich Null, wenn erfolgreich, andernfalls 0 (Null).  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `CreateEx` anstelle von [erstellen](#create) anzuwendende erweiterten Fensterstile, angegeben durch die Windows-erweiterten Stil ihm etwas voranzustellen **WS_EX_**.  
  
##  <a name="getaddress"></a>CIPAddressCtrl::GetAddress  
 Ruft die Adresswerte für alle vier Felder in die IP-Adressensteuerelement ab.  
  
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
 Ein Verweis auf den Feldwert 0 aus eine gepackte IP-Adresse.  
  
 `nField1`  
 Ein Verweis auf den Feldwert 1 aus eine gepackte IP-Adresse.  
  
 `nField2`  
 Ein Verweis auf den Feldwert 2 aus eine gepackte IP-Adresse.  
  
 `nField3`  
 Ein Verweis auf den Feldwert 3 aus eine gepackte IP-Adresse.  
  
 `dwAddress`  
 Ein Verweis auf die Adresse einer `DWORD` Wert, der die IP-Adresse empfängt. Finden Sie unter **"Hinweise"** für eine Tabelle, die zeigt, wie `dwAddress` gefüllt wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der nicht leeren Felder in die IP-Adressensteuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_GETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761378)gemäß der Beschreibung im Windows SDK. In der ersten Prototyp der Zahlen in Feldern von 0 bis 3 des Steuerelements, Lesen von links nach rechts bzw., die vier Parameter aufzufüllen. Im zweiten oben genannten Prototyp `dwAddress` wird folgendermaßen aufgefüllt.  
  
|Feld|Bits, die den Wert des Felds enthält.|  
|-----------|-------------------------------------|  
|0|24 bis 31|  
|1|16 bis 23|  
|2|8 bis 15|  
|3|0 bis 7|  
  
##  <a name="isblank"></a>CIPAddressCtrl::IsBlank  
 Bestimmt, ob alle Felder in die IP-Adressensteuerelement leer sind.  
  
```  
BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn alle IP-Adressensteuerelement Felder leer sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_ISBLANK](http://msdn.microsoft.com/library/windows/desktop/bb761379)gemäß der Beschreibung im Windows SDK.  
  
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
 Der Wert des Felds 0 aus eine gepackte IP-Adresse.  
  
 `nField1`  
 Der Wert des Felds 1 aus eine gepackte IP-Adresse.  
  
 `nField2`  
 Der Wert des Felds 2 aus eine gepackte IP-Adresse.  
  
 `nField3`  
 Der Wert des Felds 3 aus eine gepackte IP-Adresse.  
  
 `dwAddress`  
 Ein `DWORD` Wert, der die neue IP-Adresse enthält. Finden Sie unter **"Hinweise"** für eine Tabelle, die zeigt, wie die `DWORD` Wert ausgefüllt ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETADDRESS](http://msdn.microsoft.com/library/windows/desktop/bb761380)gemäß der Beschreibung im Windows SDK. In der ersten Prototyp der Zahlen in Feldern von 0 bis 3 des Steuerelements, Lesen von links nach rechts bzw., die vier Parameter aufzufüllen. Im zweiten oben genannten Prototyp `dwAddress` wird folgendermaßen aufgefüllt.  
  
|Feld|Bits, die den Wert des Felds enthält.|  
|-----------|-------------------------------------|  
|0|24 bis 31|  
|1|16 bis 23|  
|2|8 bis 15|  
|3|0 bis 7|  
  
##  <a name="setfieldfocus"></a>CIPAddressCtrl::SetFieldFocus  
 Legt den Tastaturfokus auf das angegebene Feld in die IP-Adressensteuerelement fest.  
  
```  
void SetFieldFocus(WORD nField);
```  
  
### <a name="parameters"></a>Parameter  
 `nField`  
 Nullbasierte Feldindex, zu dem der Fokus festgelegt werden soll. Wenn dieser Wert größer als die Anzahl der Felder ist, wird dem ersten leeren Feld Fokus festgelegt werden. Wenn alle Felder nicht leer sind, wird den Fokus auf das erste Feld festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETFOCUS](http://msdn.microsoft.com/library/windows/desktop/bb761381)gemäß der Beschreibung im Windows SDK.  
  
##  <a name="setfieldrange"></a>CIPAddressCtrl::SetFieldRange  
 Legt den Bereich im angegebenen Feld in die IP-Adressensteuerelement fest.  
  
```  
void SetFieldRange(
    int nField,  
    BYTE nLower,  
    BYTE nUpper);
```  
  
### <a name="parameters"></a>Parameter  
 `nField`  
 Nullbasierte Feldindex auf die der Bereich angewendet werden soll.  
  
 `nLower`  
 Ein Verweis auf eine ganze Zahl, die die Untergrenze des angegebenen Felds in diese IP-Adressensteuerelement empfangen.  
  
 `nUpper`  
 Ein Verweis auf eine ganze Zahl, die die Obergrenze des angegebenen Felds in diese IP-Adressensteuerelement empfangen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Nachricht [IPM_SETRANGE](http://msdn.microsoft.com/library/windows/desktop/bb761382)gemäß der Beschreibung im Windows SDK. Verwenden Sie die beiden Parameter `nLower` und `nUpper`, um den oberen und unteren Grenzen des Felds, anstelle von anzugeben, die *wRange* Parameter mit der Win32-Nachricht verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



