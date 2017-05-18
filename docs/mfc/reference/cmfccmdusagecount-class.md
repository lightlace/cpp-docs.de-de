---
title: Klasse CMFCCmdUsageCount | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::AddCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::GetCount
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::HasEnoughInformation
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::IsFreqeuntlyUsedCmd
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Reset
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::Serialize
- AFXCMDUSAGECOUNT/CMFCCmdUsageCount::SetOptions
dev_langs:
- C++
helpviewer_keywords:
- CMFCCmdUsageCount class
ms.assetid: 9c33b783-37c0-43ea-9f31-3c75e246c841
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: b264448af4041139018b181e2255988555267b89
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccmdusagecount-class"></a>CMFCCmdUsageCount-Klasse
Überwacht die Verwendungsanzahl der Windows-Meldungen, z. B. wenn der Benutzer ein Element aus einem Menü auswählt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCCmdUsageCount : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`CMFCCmdUsageCount::CMFCCmdUsageCount`|Standardkonstruktor|  
|`CMFCCmdUsageCount::~CMFCCmdUsageCount`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|||  
|-|-|  
|Name|Beschreibung|  
|[CMFCCmdUsageCount::AddCmd](#addcmd)|Inkrementiert um eins der Zähler, der den angegebenen Befehl zugeordnet ist.|  
|[CMFCCmdUsageCount::GetCount](#getcount)|Ruft die Verwendungsanzahl, die der angegebenen Befehls-ID zugeordnet ist.|  
|[CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation)|Bestimmt, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt hat.|  
|[CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd)|Bestimmt, ob der angegebene Befehl häufig verwendet wird.|  
|[CMFCCmdUsageCount::Reset](#reset)|Löscht die Verwendungsanzahl aller Befehle.|  
|[CMFCCmdUsageCount::Serialize](#serialize)|Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv. (Überschreibt [Einfügeoperatoren](../../mfc/reference/cobject-class.md#serialize).)|  
|[CMFCCmdUsageCount::SetOptions](#setoptions)|Legt die Werte der freigegebenen `CMFCCmdUsageCount` Klassendatenmember.|  
  
### <a name="data-members"></a>Datenmember  
  
|||  
|-|-|  
|Name|Beschreibung|  
|`m_CmdUsage`|Ein `CMap` -Objekt, das die Verwendungszähler Befehlen zuordnet.|  
|`m_nMinUsagePercentage`|Die minimale Auslastung in Prozent für einen Befehl häufig verwendet werden.|  
|`m_nStartCount`|Der Start-Zähler, der verwendet wird, um festzustellen, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt hat.|  
|`m_nTotalUsage`|Die Anzahl der alle überwachten Befehle.|  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCCmdUsageCount` -Klasse ordnet jeder numerischen Windows-Nachrichten-ID in einen Leistungsindikator für die 32-Bit-Ganzzahl ohne Vorzeichen. `CMFCToolBar`Mithilfe dieser Klasse häufig verwendete Elemente angezeigt. Weitere Informationen zu `CMFCToolBar`, finden Sie unter [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md).  
  
 Sie können beibehalten `CMFCCmdUsageCount` -Klasse Daten zwischen der Ausführung des Programms. Verwenden der [CMFCCmdUsageCount::Serialize](#serialize) -Methode zum Serialisieren von Daten und die [CMFCCmdUsageCount::SetOptions](#setoptions) Methode zum Festlegen der freigegebenen Members.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCCmdUsageCount](../../mfc/reference/cmfccmdusagecount-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcmdusagecount.h  
  
##  <a name="addcmd"></a>CMFCCmdUsageCount::AddCmd  
 Inkrementiert um eins der Zähler, der den angegebenen Befehl zugeordnet ist.  
  
```  
void AddCmd(UINT uiCmd);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `uiCmd`|Gibt den Befehl Zähler inkrementiert.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt einen neuen Eintrag zur Zuordnung Struktur der Befehl Anzahl der `m_CmdUsage`, wenn der Eintrag nicht vorhanden ist.  
  
 Diese Methode bewirkt nichts in den folgenden Fällen:  
  
-   Die Symbolleiste-Framework ist im Anpassungsmodus (die [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode) -Methode gibt einen Wert ungleich NULL zurück).  
  
-   Der Befehl bezieht sich auf ein Untermenü oder Menü Trennzeichen ( `uiCmd` ist gleich 0 oder-1).  
  
- `uiCmd`bezieht sich auf einen Standardbefehl (die global `IsStandardCommand` Funktion gibt einen Wert ungleich NULL zurück).  
  
##  <a name="getcount"></a>CMFCCmdUsageCount::GetCount  
 Ruft die Verwendungsanzahl, die der angegebenen Befehls-ID zugeordnet ist.  
  
```  
UINT GetCount(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `uiCmd`|Die ID des Leistungsindikators Befehl abrufen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Die Verwendungsanzahl, die der angegebenen Befehls-ID zugeordnet ist.  
  
##  <a name="hasenoughinformation"></a>CMFCCmdUsageCount::HasEnoughInformation  
 Bestimmt, ob dieses Objekt die Mindestmenge an Verfolgungsdaten empfangen hat.  
  
```  
BOOL HasEnoughInformation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn dieses Objekt die Mindestmenge an Verfolgungsdaten erhalten hat; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt einen Wert ungleich NULL zurück, wenn die Gesamtanzahl `m_nTotalUsage`, der alle überwachten Befehle ist gleich oder größer als die Anzahl der anfänglichen `m_nStartCount`. Standardmäßig legt das Framework die anfängliche Anzahl 0. Sie können diesen Wert überschreiben, indem die [CMFCCmdUsageCount::SetOptions](#setoptions) Methode.  
  
 Diese Methode wird verwendet, indem [CMFCMenuBar::IsShowAllCommands](../../mfc/reference/cmfcmenubar-class.md#isshowallcommands) zu bestimmen, ob alle im Kontextmenü verfügbaren Befehle anzuzeigen.  
  
##  <a name="isfreqeuntlyusedcmd"></a>CMFCCmdUsageCount::IsFreqeuntlyUsedCmd  
 Bestimmt, ob der angegebene Befehl häufig verwendet wird.  
  
```  
BOOL IsFreqeuntlyUsedCmd(UINT uiCmd) const;  
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `uiCmd`|Gibt den Befehl überprüfen.|  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Befehl häufig verwendet wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt 0 zurück, wenn die gesamte Befehlssyntax `m_nTotalUsage`, ist 0. Andernfalls gibt diese Methode einen Wert ungleich NULL, wenn der Prozentsatz der wird der Befehl verwendet den Mindestprozentsatz übersteigt `m_nMinUsagePercentage`. Standardmäßig legt das Framework den Mindestprozentsatz auf 5 fest. Sie können diesen Wert überschreiben, indem die [CMFCCmdUsageCount::SetOptions](#setoptions) Methode. Wenn Sie der Mindestprozentsatz 0 ist, gibt diese Methode einen Wert ungleich NULL, wenn die angegebene Anzahl größer als 0 ist.  
  
 [CMFCToolBar::IsCommandRarelyUsed](../../mfc/reference/cmfctoolbar-class.md#iscommandrarelyused) verwendet diese Methode, um zu bestimmen, ob ein Befehl nur selten verwendet wird.  
  
##  <a name="reset"></a>CMFCCmdUsageCount::Reset  
 Löscht die Verwendungsanzahl aller Befehle.  
  
```  
void Reset();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, um alle Einträge aus der Struktur der Zuordnung der Befehl Anzahl der löschen `m_CmdUsage`, und der gesamte Befehl Zurücksetzen `m_nTotalUsage`, Zähler auf 0.  
  
##  <a name="serialize"></a>CMFCCmdUsageCount::Serialize  
 Dieses Objekt aus dem Archiv liest oder schreibt dieses in ein Archiv.  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `ar`|Ein `CArchive` zu von oder zu serialisierende Objekt.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode serialisiert die Struktur der Zuordnung der Befehl Anzahl der `m_CmdUsage`, und die gesamte Befehlssyntax `m_nTotalUsage`, Zähler von oder in das angegebene Archiv.  
  
 Beispiele zur Serialisierung finden Sie [Serialisierung: Serialisieren eines Objekts](../../mfc/serialization-serializing-an-object.md).  
  
##  <a name="setoptions"></a>CMFCCmdUsageCount::SetOptions  
 Legt die Werte der freigegebenen `CMFCCmdUsageCount` Klassendatenmember.  
  
```  
static BOOL __stdcall SetOptions(
    UINT nStartCount,  
    UINT nMinUsagePercentage);
```  
  
### <a name="parameters"></a>Parameter  
  
|||  
|-|-|  
|Parameter|Beschreibung|  
|[in] `nStartCount`|Die anfängliche Anzahl neuer alle überwachten Befehle.|  
|[in] `nMinUsagePercentage`|Die neue minimale Auslastung in Prozent.|  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist, `FALSE` Wenn der `nMinUsagePercentage` Parameter ist größer als oder gleich 100.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode legt den gemeinsam genutzten `CMFCCmdUsageCount` Klassendatenmember `m_nStartCount` und `m_nMinUsagePercentage` auf `nStartCount` und `nMinUsagePercentage`bzw.. `m_nStartCount`werden die [CMFCCmdUsageCount::HasEnoughInformation](#hasenoughinformation) Methode, um zu bestimmen, ob dieses Objekt die Mindestmenge an Überwachungsdaten gesammelt hat. `m_nMinUsagePercentage`werden die [CMFCCmdUsageCount::IsFreqeuntlyUsedCmd](#isfreqeuntlyusedcmd) Methode, um zu bestimmen, ob ein bestimmter Befehl häufig verwendet wird.  
  
 In Debugbuilds generiert diese Methode eine Assertionsfehler ausgelöst, wenn der `nMinUsagePercentage` Parameter ist größer als oder gleich 100.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)

