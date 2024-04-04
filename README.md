Requires: Node.js installed  

Run:  

```
npm install
node index.js`
```



```
/****

    Here are examples of XMLs returned:


    1. When usign wrong password:


    <S:Envelope xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:S="http://www.w3.org/2003/05/soap-envelope">
	<S:Header>
		<psf:pp xmlns:psf="http://schemas.microsoft.com/Passport/SoapServices/SOAPFault">
			<psf:serverVersion>1</psf:serverVersion>
			<psf:authstate>0x80048800</psf:authstate>
			<psf:reqstatus>0x80048821</psf:reqstatus>
			<psf:serverInfo ServerTime="2024-04-03T19:40:33.3501755Z">ESTS-PUB-SCUS-LZ3-FD081-001.ProdSlices rid:c887b098-4934-4d3c-9a96-e929108c4f01</psf:serverInfo>
		</psf:pp>
	</S:Header>
	<S:Body xmlns:S="http://www.w3.org/2003/05/soap-envelope">
		<S:Fault>
			<S:Code>
				<S:Value>S:Sender</S:Value>
				<S:Subcode>
					<S:Value>wst:FailedAuthentication</S:Value>
				</S:Subcode>
			</S:Code>
			<S:Reason>
				<S:Text xml:lang="en-US">Authentication Failure</S:Text>
			</S:Reason>
			<S:Detail>
				<psf:error xmlns:psf="http://schemas.microsoft.com/Passport/SoapServices/SOAPFault">
					<psf:value>0x80048821</psf:value>
					<psf:internalerror>
						<psf:code>0x80048821</psf:code>
						<psf:text>AADSTS50126: Error validating credentials due to invalid username or password.</psf:text>
					</psf:internalerror>
				</psf:error>
			</S:Detail>
		</S:Fault>
	</S:Body>
</S:Envelope>



2. When using proper password:
 
<?xml version="1.0" encoding="utf-8"?>
<S:Envelope xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:S="http://www.w3.org/2003/05/soap-envelope">
	<S:Header>
		<wsa:Action S:mustUnderstand="1" wsu:Id="Action">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue</wsa:Action>
		<wsa:To S:mustUnderstand="1" wsu:Id="To">http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</wsa:To>
		<wsse:Security S:mustUnderstand="1">
			<wsu:Timestamp wsu:Id="TS" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
				<wsu:Created>2024-04-03T19:42:30.2761061Z</wsu:Created>
				<wsu:Expires>2024-04-03T19:47:30.2761061Z</wsu:Expires>
			</wsu:Timestamp>
		</wsse:Security>
	</S:Header>
	<S:Body xmlns:S="http://www.w3.org/2003/05/soap-envelope">
		<wst:RequestSecurityTokenResponse xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust">
			<wsp:AppliesTo>
				<wsa:EndpointReference xmlns:wsa="http://www.w3.org/2005/08/addressing">
					<wsa:Address>https://vanderbilt365.sharepoint.com/_forms/default.aspx?wa=wsignin1.0</wsa:Address>
				</wsa:EndpointReference>
			</wsp:AppliesTo>
			<psf:pp xmlns:psf="http://schemas.microsoft.com/Passport/SoapServices/SOAPFault">
				<psf:reqstatus>0x8004882c</psf:reqstatus>
				<psf:errorstatus>0x80045b00</psf:errorstatus>
			</psf:pp>
		</wst:RequestSecurityTokenResponse>
	</S:Body>
</S:Envelope>


3. Successful response when using the same code with another customer


<?xml version="1.0" encoding="utf-8"?>
<S:Envelope xmlns:wsa="http://www.w3.org/2005/08/addressing" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" xmlns:S="http://www.w3.org/2003/05/soap-envelope">
	<S:Header>
		<wsa:Action S:mustUnderstand="1" wsu:Id="Action">http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue</wsa:Action>
		<wsa:To S:mustUnderstand="1" wsu:Id="To">http://schemas.xmlsoap.org/ws/2004/08/addressing/role/anonymous</wsa:To>
		<wsse:Security S:mustUnderstand="1">
			<wsu:Timestamp wsu:Id="TS" xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">
				<wsu:Created>2024-04-04T03:42:08.6387485Z</wsu:Created>
				<wsu:Expires>2024-04-04T03:47:08.6387485Z</wsu:Expires>
			</wsu:Timestamp>
		</wsse:Security>
	</S:Header>
	<S:Body xmlns:S="http://www.w3.org/2003/05/soap-envelope">
		<wst:RequestSecurityTokenResponse xmlns:wsu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd" xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy" xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust">
			<wst:TokenType>urn:passport:compact</wst:TokenType>
			<wsp:AppliesTo>
				<wsa:EndpointReference xmlns:wsa="http://www.w3.org/2005/08/addressing">
					<wsa:Address>https://___REDACTED___.sharepoint.com/_forms/default.aspx?wa=wsignin1.0</wsa:Address>
				</wsa:EndpointReference>
			</wsp:AppliesTo>
			<wst:Lifetime>
				<wsu:Created>2024-04-04T03:42:08Z</wsu:Created>
				<wsu:Expires>2024-04-05T03:42:08Z</wsu:Expires>
			</wst:Lifetime>
			<wst:RequestedSecurityToken>
				<wsse:BinarySecurityToken Id="Compact0" xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">t=EwDYAk6hBwAU1EFiFzob88onaFY+I6On0nScVqEAAVFNIqgsmJoFVE5c3A7pzHBBiJpFpMxst/qCiWLJy4VBDRMzFB+SrxJ+2FOoj4nnn02+9Iaa0v3qWD4R+tkhtgnZW5K+ZeqkbmwIoiVosjaTjYCkmvCqWzuFzg5iTsSN9h0ZF45kC2oX8mLgYXRlLgabe07w4oOeNeapb3divNDxvqXhvN5aOqPNYrtNyd2vOEasE1idrBGX9fenJHzrMhrUGl3KB15e4GLr/xI0zRJBgeXjqkhRRXKvfEu/T5dibvJ3y11XpsjGYKj7BB9+EvLI/jb1gECGyNnw0zh+xyA3UEtPND7qI9IgCJQ10rvPJ9PN/7ormZIIrsCX90sJInMDZgAACFrlEVaIKRzhqAE4x7MnDZnNHv3Sx1j8yiMzowEj3t3upAJfPKC2Cg6jZlsyuhF49zNQjHwKgAza7bFwy5EJoH0CaCtPIk0ydmq+KpzHXc0Q+rpGtPTPeCnTL/y9CyuF7RBopD86fpwbHZr8ZJ5wdCNREusTBqsgMBxaHNFK+KcX4Ni/++B7AhxvHXRCmiUU76U2NGK9sfuINKBWsHXYgAIpy2FffzVcuEQnh8Mff9Y+v//MDY+ZVmVzqnrNjjNA2J7F+wDYdreDBp3GoODCWKe3R/zy/hHR4E6O/YhPeI1a5WSqmnPACOEXmxvuL8D57Z86pu2w75IGdfAE/5tsWGN7QuqrioOvNYwenPGc20HsNctaU/1LTDtCimq0zdJ2EGEtQSHEbSpf2RQZ7EeXwPZ3ORWCOYN3bmTjix28U+fgVqhzjndiUKkyS5EYOXWrmauT88kquVx12o3UDInCKMdIVWqzmabElCm7GDGWLTbqWIRQJf5EfBqRU+DvSv56gbSLoQT/CxMKNxj+TbjUBG9XwdqCZmedxWOz+NF86GMD5fiGrElk/YbwXUFFOQVg+TUuBgI=&amp;p=</wsse:BinarySecurityToken>
			</wst:RequestedSecurityToken>
			<wst:RequestedAttachedReference>
				<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
					<wsse:Reference URI="F9lH5Y+80Bs7hz++O9ARULPHFTE=">
					</wsse:Reference>
				</wsse:SecurityTokenReference>
			</wst:RequestedAttachedReference>
			<wst:RequestedUnattachedReference>
				<wsse:SecurityTokenReference xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">
					<wsse:Reference URI="F9lH5Y+80Bs7hz++O9ARULPHFTE=">
					</wsse:Reference>
				</wsse:SecurityTokenReference>
			</wst:RequestedUnattachedReference>
		</wst:RequestSecurityTokenResponse>
	</S:Body>
</S:Envelope>


 * 
 */

```
