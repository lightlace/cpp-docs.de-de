---
title: "CComCurrency Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CComCurrency"
  - "ATL.CComCurrency"
  - "ATL::CComCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComCurrency class"
ms.assetid: a1c3d10a-bba6-40cc-8bcf-aed9023c8a9e
caps.latest.revision: 21
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CComCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CComCurrency` verfügt über Methoden und Operatoren zum Erstellen und Verwalten eines CURRENCY\-Objekts.  
  
## Syntax  
  
```  
  
class CComCurrency  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComCurrency::CComCurrency](../Topic/CComCurrency::CComCurrency.md)|Der Konstruktor für ein `CComCurrency`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComCurrency::GetCurrencyPtr](../Topic/CComCurrency::GetCurrencyPtr.md)|Gibt die Adresse eines `m_currency`\-Datenmembers zurück.|  
|[CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md)|Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`\-Objekts zurückzugeben.|  
|[CComCurrency::GetInteger](../Topic/CComCurrency::GetInteger.md)|Rufen Sie diese Methode auf, um die ganzzahlige Komponente eines `CComCurrency`\-Objekts zurückzugeben.|  
|[CComCurrency::Round](../Topic/CComCurrency::Round.md)|Rufen Sie diese Methode auf, um ein `CComCurrency`\-Objekt auf den nächsten ganzzahligen Wert zu runden.|  
|[CComCurrency::SetFraction](../Topic/CComCurrency::SetFraction.md)|Rufen Sie diese Methode auf, um den Nachkommawert eines `CComCurrency`\-Objekts festzulegen.|  
|[CComCurrency::SetInteger](../Topic/CComCurrency::SetInteger.md)|Rufen Sie diese Methode auf, um den ganzzahligen Wert eines `CComCurrency`\-Objekts festzulegen.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComCurrency::operator \-](../Topic/CComCurrency::operator%20-2.md)|Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`\-Objekt auszuführen.|  
|[CComCurrency::operator \!\=](../Topic/CComCurrency::operator%20!=.md)|Überprüft zwei `CComCurrency`\-Objekte auf Ungleichheit.|  
|[CComCurrency::operator \*](../Topic/CComCurrency::operator%20*.md)|Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`\-Objekt auszuführen.|  
|[CComCurrency::operator \*\=](../Topic/CComCurrency::operator%20*=.md)|Dieser Operator wird verwendet, um Multiplikation für ein `CComCurrency`\-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|  
|[CComCurrency::operator \/](../Topic/CComCurrency::operator%20-1.md)|Dieser Operator wird verwendet, um Division für ein `CComCurrency`\-Objekt auszuführen.|  
|[CComCurrency::operator \/\=](../Topic/CComCurrency::operator%20-=2.md)|Dieser Operator wird verwendet, um Division für ein `CComCurrency`\-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|  
|[CComCurrency::operator \+](../Topic/CComCurrency::operator%20+.md)|Dieser Operator wird verwendet, um Addition für ein `CComCurrency`\-Objekt auszuführen.|  
|[CComCurrency::operator \+\=](../Topic/CComCurrency::operator%20+=.md)|Dieser Operator wird verwendet, um Addition für ein `CComCurrency`\-Objekt auszuführen und das Ergebnis dem aktuellen Objekt zuzuweisen.|  
|[CComCurrency::operator \<](../Topic/CComCurrency::operator%20%3C.md)|Dieser Operator vergleicht zwei `CComCurrency`\-Objekte, um das kleinere zu bestimmen.|  
|[CComCurrency::operator \<\=](../Topic/CComCurrency::operator%20%3C=.md)|Dieser Operator vergleicht zwei `CComCurrency`\-Objekte, um zu bestimmen, ob sie gleich sind oder welches kleiner ist.|  
|[CComCurrency::operator \=](../Topic/CComCurrency::operator%20=.md)|Dieser Operator weist dem `CComCurrency`\-Objekt einen neuen Wert zu.|  
|[CComCurrency::operator \-\=](../Topic/CComCurrency::operator%20-=1.md)|Dieser Operator wird verwendet, um Subtraktion für ein `CComCurrency`\-Objekt auszuführen und ihm das Ergebnis zuzuweisen.|  
|[CComCurrency::operator \=\=](../Topic/CComCurrency::operator%20==.md)|Dieser Operator überprüft zwei `CComCurrency`\-Objekte auf Gleichheit.|  
|[CComCurrency::operator \>](../Topic/CComCurrency::operator%20%3E.md)|Dieser Operator vergleicht zwei `CComCurrency`\-Objekte, um das größere zu bestimmen.|  
|[CComCurrency::operator \>\=](../Topic/CComCurrency::operator%20%3E=.md)|Dieser Operator vergleicht zwei `CComCurrency`\-Objekte, um zu bestimmen, ob sie gleich sind oder welches größer ist.|  
|[CComCurrency::operator CURRENCY](../Topic/CComCurrency::operator%20CURRENCY.md)|Wandelt ein `CURRENCY`\-Objekt um.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CComCurrency::m\_currency](../Topic/CComCurrency::m_currency.md)|Die `CURRENCY`\-Variable, die von der Klasseninstanz erstellt wurde.|  
  
## Hinweise  
 `CComCurrency` ist ein Wrapper für den **CURRENCY**\-Datentyp.  **CURRENCY** ist als ganzzahliger 8\-Byte\-Zweierkomplementwert, skaliert mit 10.000, implementiert.  Dies ermöglicht eine Festkommazahl mit 15 Stellen links vom Dezimaltrennzeichen und 4 Ziffern rechts.  Der Datentyp **CURRENCY** ist äußerst nützlich für Finanzberechnungen oder für Festkommaberechnungen, bei denen Genauigkeit wichtig ist.  
  
 Der **CComCurrency**\-Wrapper implementiert arithmetische, Zuweisungs\- und Vergleichsoperationen für diesen Festkommatyp.  Die unterstützten Anwendungen wurden ausgewählt, um die Rundungsfehler zu steuern, die während der Festkommaberechnungen auftreten können.  
  
 Das `CComCurrency`\-Objekt bietet Zugriff auf die Zahlen auf beiden Seiten des Dezimaltrennzeichens in der Form von zwei Komponenten: eine Ganzzahlkomponente, die den Wert links vom Dezimalzeichen speichert, und eine Nachkommakomponente, die den Wert rechts vom Dezimalzeichen speichert.  Der Nachkommawert wird intern als eine ganze Zahl zwischen \-9999 \(**CY\_MIN\_FRACTION**\) und \+9999 \(**CY\_MAX\_FRACTION**\) gespeichert.  Die Methode [CComCurrency::GetFraction](../Topic/CComCurrency::GetFraction.md) gibt einen Wert zurück, der mit einem Faktor von 10.000 skaliert \(**CY\_SCALE**\) wurde.  
  
 Beachten Sie bei der Angabe der Ganzzahl\- und Nachkommakomponenten eines **CComCurrency**\-Objekts, dass der Nachkommawert eine Zahl im Bereich von 0 bis 9999 ist.  Dies ist bei einer Währung wie z. B. dem US\-Dollar wichtig, bei der die Summen nur mit zwei signifikante Ziffern nach dem Dezimaltrennzeichen ausgedrückt werden.  Obwohl die letzten zwei Ziffern nicht angezeigt werden, müssen sie berücksichtigt werden.  
  
|Wert|Mögliche CComCurrency\-Zuweisungen|  
|----------|----------------------------------------|  
|$10.50|CComCurrency\(10,5000\) *oder* CComCurrency\(10.50\)|  
|$10.05|CComCurrency\(10,500\) *oder* CComCurrency\(10.05\)|  
  
 Die Werte **CY\_MIN\_FRACTION**, **CY\_MAX\_FRACTION** und **CY\_SCALE** sind in „atlcur.h“ definiert.  
  
## Anforderungen  
 **Header:** atlcur.h  
  
## Siehe auch  
 [COleCurrency Class](../../mfc/reference/colecurrency-class.md)   
 [CURRENCY](assetId:///5e81273c-7289-45c7-93c0-32c1553f708e)   
 [Class Overview](../../atl/atl-class-overview.md)