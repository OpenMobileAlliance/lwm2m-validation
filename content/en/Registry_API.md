---
title: Registry API
description: ''
position: 2
category: ''
---
<style>
    table {
      border-collapse: collapse;
      width: 100%;
    }
    td, th {
      border: 1px solid #1f1e1e;
      text-align: left;
      padding: 10px;
    }
    th {
        background-color: #ebeaea;
        text-align: left;
        font-weight: bold;
    }
    .td-30 { 
        width: 30%;
    }
    .prose tbody td:first-child {
        padding-left: 10px;
    }
    .prose thead th:first-child {
        padding-left: 10px;
    }
</style>
    
This page provides all the necessary information to interact with the OMA Registry, also called OMNA (OMA Naming
Authority).

## Base URL for this Registry API

http://www.openmobilealliance.org/api/

## OMA LwM2M Registry API Functions, V1

This table list what functions are available on the OMA LwM2M Registry API version 1.

This API provide access to the content on the LwM2M Registry.

<table>
    <thead>
        <tr>
            <th>Basic Function</th>
            <th>URL</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2" class="td-30">Objects Discovery</td>
            <td>
                <a href="http://www.openmobilealliance.org/api/lwm2m/v1/Object">lwm2m/v1/Object</a>
            </td>
            <td>Retrieve a JSON file containing all the metadata information on all the Object
                Versions.</td>
        </tr>
        <tr>
            <td>
                <a href="http://www.openmobilealliance.org/api/lwm2m/v1/Object?ObjectVersion=latest">lwm2m/v1/Object?ObjectVersion=latest</a>
            </td>
            <td>
                <p>Retrieve a JSON file containing all the metadata information with the latest version of the Objects
                </p>
            </td>
        </tr>
        <tr>
            <td rowspan="3" class="td-30">Get an Object<br><br><br></td>
            <td>
                <a href="http://www.openmobilealliance.org/api/lwm2m/v1/Object?ObjectID=12">lwm2m/v1/Object?ObjectID=12</a>
            </td>
            <td>Retrieve a JSON file containing metadata information on Object 12</td>
        </tr>
        <tr>
            <td>
                <a href="http://www.openmobilealliance.org/api/lwm2m/v1/Object?ObjectID=12&amp;ObjectVersion=latest">lwm2m/v1/Object?ObjectID=12&amp;ObjectVersion=latest</a>
            </td>
            <td>
                <p>Retrieve a JSON file containing metadata information with the latest version of Object 12.</p>
            </td>
        </tr>
        <tr>
            <td>
                <a href="http://www.openmobilealliance.org/api/lwm2m/v1/Object?ObjectID=12&amp;ObjectVersion=1.0">lwm2m/v1/Object?ObjectID=12&amp;ObjectVersion=1.0</a>
            </td>
            <td>
                Retrieve a JSON file containing metadata information on Object Version 1.0 of Object 12.
            </td>
        </tr>
    </tbody>
</table>

Note: In case of ObjectVersion is included with different value than ”latest” then ObjectID must be included.

## Error Codes

<table>
    <thead>
        <tr>
            <th>HTTP Code</th>
            <th>Error Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>400</td>
            <td>
                <p>ObjectID must be included when ObjectVersion is set to "latest".</p>
            </td>
        </tr>
        <tr>
            <td>404</td>
            <td>Specified ObjectID and/or ObjectVersion is not in the Registry.</td>
        </tr>
    </tbody>
</table>

## Metadata Information

This is the metadata information that will be available via this API. This information is not the content of the Object
but the metadata information that defines or classifies the Object itself in our system.

<table>
    <thead>
        <tr>
            <th>Element</th>
            <th>Description</th>
        </tr>
    <tbody>
        <tr>
            <td colspan="1"><span style="color: rgb(136,18,128);">&lt;VortoLink&gt;</span>
            </td>
            <td colspan="1">URL to this object in Vorto</td>
        </tr>
        <tr>
            <td><span style="color: rgb(136,18,128);">&lt;Ver</span><span
                    style="color: rgb(136,18,128);">&gt;</span></td>
            <td>Version of the Object</td>
        </tr>
        <tr>
            <td colspan="1"><span style="color: rgb(136,18,128);">&lt;URN&gt;</span></td>
            <td colspan="1">Object unique URN</td>
        </tr>
        <tr>
            <td><span style="color: rgb(136,18,128);">&lt;SpecLinkVisible</span><span
                    style="color: rgb(136,18,128);">&gt;</span></td>
            <td>
                <ul>
                    <li>0 =&gt; if the link to the TS should not be visible,</li>
                    <li>1 =&gt; if the link to the TS should be visible</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td><span style="color: rgb(136,18,128);">&lt;SpecLink&gt;</span></td>
            <td>URL to the Technical Specifications (TS)</td>
        </tr>
        <tr>
            <td colspan="1"><span style="color: rgb(136,18,128);">&lt;Owner&gt;</span></td>
            <td colspan="1">Name of the organization that has registered the Object</td>
        </tr>
        <tr>
            <td><span style="color: rgb(136,18,128);">&lt;ObjectLinkVisible&gt;</span></td>
            <td>
                <ul>
                    <li>0 =&gt; if the link to the Object should not be visible,</li>
                    <li>1 =&gt; if link to the Object should be visible,</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td><span style="color: rgb(136,18,128);">&lt;ObjectLink&gt;</span></td>
            <td>URL to the xml file describing the Object.</td>
        </tr>
        <tr>
            <td><span style="color: rgb(136,18,128);">&lt;ObjectID&gt;</span></td>
            <td>Object ID.</td>
        </tr>
        <tr>
            <td colspan="1"><span style="color: rgb(136,18,128);">&lt;Name&gt;</span></td>
            <td colspan="1">Object Name.</td>
        </tr>
        <tr>
            <td colspan="1"><span style="color: rgb(136,18,128);">&lt;Label&gt;</span></td>
            <td colspan="1">
                <p>Who has defined the Object:</p>
                <ul>
                    <li>0 = defined by OMA</li>
                    <li>1 = defined by external Standards Development Organization</li>
                    <li>2 = private or individual registration</li>
                </ul>
            </td>
        </tr>
        <tr>
            <td colspan="1"><span style="color: rgb(136,18,128);">&lt;Description&gt;</span></td>
            <td colspan="1">Description of the Object.</td>
        </tr>
    </tbody>
</table>