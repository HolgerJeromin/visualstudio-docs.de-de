---
title: XML-Tools in Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
f1_keywords:
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 446378df2d73f4d0c2bb8eac45075fa51365cd6d
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693733"
---
# <a name="xml-tools-in-visual-studio"></a>XML-Tools in Visual Studio

*Extensible Markup Language (XML)* ist eine Markupsprache, die ein Format zum Beschreiben von Daten bereitstellt. Dies erleichtert eine präzisere Deklaration von Inhalt und bietet vertrauenswürdigere Suchergebnisse auf verschiedenen Plattformen. Darüber hinaus ermöglicht XML die Trennung von Präsentationsinformationen und Daten. Bei HTML verwenden Sie beispielsweise Tags, um den Browser anzuweisen, dass Daten fett oder kursiv dargestellt werden; bei XML verwenden Sie Tags nur, um Daten zu beschreiben, z. B. den Namen einer Stadt, die Temperatur oder den Luftdruck. Im XML-verwenden Sie Stylesheets wie Extensible Stylesheet Language (XSL) und cascading Stylesheets (CSS), um die Daten in einem Browser darzustellen. XML trennt die Daten von den Präsentationsinformationen und dem Prozess. Dadurch können Sie die Daten wie gewünscht anzeigen und verarbeiten, indem Sie verschiedene Stylesheets und Anwendungen anwenden.

XML ist ein Teilsatz von SGML, der für die Bereitstellung über das Internet optimiert wurde. Es wird vom World Wide Web Consortium (W3C) definiert. Diese Standardisierung stellt sicher, dass strukturierte Daten einheitlich und von Anwendungen oder Anbietern unabhängig sind.

XML ist die Grundlage vieler Funktionen von Visual Studio und .NET Framework. Die folgenden Artikelliste enthält die Tools und Funktionen im Zusammenhang mit XML, die in Visual Studio und .NET Framework bereitgestellt werden.

Weitere Informationen finden Sie unter der <xref:System.Xml?displayProperty=fullName> Dokumentation.

## <a name="reference"></a>Referenz

[Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699) macht die [XML-Editor](http://go.microsoft.com/fwlink/?LinkId=228249) Analysestruktur über ["System.Xml.Linq"](http://go.microsoft.com/fwlink/?LinkId=228250) für alle XML-Dokumente.

[Referenzen zu XML-Standards](http://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401) enthält Informationen zu XML-Technologien, einschließlich XML, Document Type Definition (DTD), XML-Schemadefinitionssprache (XSD) und XSLT.

<xref:System.Xml?displayProperty=fullName> Beschreibt die Klassen und andere Elemente, aus denen die <xref:System.Xml> Namespace und bietet Links zu ausführlicheren Informationen über jedes Element.

<xref:System.Xml.Serialization?displayProperty=fullName> Beschreibt die Klassen und andere Elemente, aus denen die <xref:System.Xml.Serialization> Namespace und enthält Links zu ausführlicheren Informationen zu den einzelnen Elementen.

## <a name="related-sections"></a>Verwandte Abschnitte

[(XML-DOKUMENTOBJEKTMODELL)](/dotnet/standard/data/xml/xml-document-object-model-dom) beschreibt wie die <xref:System.Xml.XmlDocument> und die zugehörigen Klassen mit dem W3C Document Object Model (Core) Level 1 und Level 2 Namespace Support-Spezifikationen entsprechen.

[Verarbeiten von XML-Daten mit "XmlReader" und "XmlWriter"](https://msdn.microsoft.com/library/cc189001(v=vs.95).aspx)

[XSLT-Transformationen](/dotnet/standard/data/xml/xslt-transformations) beschreibt wie die <xref:System.Xml.Xsl.XslCompiledTransform> Klasse implementiert die Empfehlung zu XSLT 1.0.

[Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells](/dotnet/standard/data/xml/process-xml-data-using-the-xpath-data-model) beschreibt wie die <xref:System.Xml.XPath.XPathNavigator> Klasse kann gespeicherte XML-Daten verarbeiten einer <xref:System.Xml.XPath.XPathDocument> oder ein <xref:System.Xml.XmlDocument> Objekt. Die <xref:System.Xml.XPath.XPathNavigator>-Klasse basiert auf dem XQuery 1.0- und XPath 2.0-Datenmodell und kann zum Navigieren und Bearbeiten von XML-Daten verwendet werden.

[(XML-Schemaobjektmodell)](/dotnet/standard/data/xml/xml-schema-object-model-som) beschreibt die Klassen, die zum Erstellen und Bearbeiten von XML-Schemas, durch die Bereitstellung einer <xref:System.Xml.Schema.XmlSchema> Klasse zum Laden und Bearbeiten eines Schemas.