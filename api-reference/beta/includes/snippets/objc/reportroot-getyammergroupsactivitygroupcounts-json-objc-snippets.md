---
description: "Automatically generated file. DO NOT MODIFY"
---

```objc

MSHTTPClient *httpClient = [MSClientFactory createHTTPClientWithAuthenticationProvider:authenticationProvider];

NSString *MSGraphBaseURL = @"https://graph.microsoft.com/beta/";
NSMutableURLRequest *urlRequest = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:[MSGraphBaseURL stringByAppendingString:@"/reports/getYammerGroupsActivityGroupCounts(period='D7')?$format=application/json"]]];
[urlRequest setHTTPMethod:@"GET"];

MSURLSessionDataTask *meDataTask = [httpClient dataTaskWithRequest:urlRequest 
	completionHandler: ^(NSData *data, NSURLResponse *response, NSError *nserror) {

		NSError *jsonError = nil;
		NSDictionary *jsonFinal = [NSJSONSerialization JSONObjectWithData:data options:0 error:&jsonError];
		NSMutableArray *yammerGroupsActivityGroupCountsList = [[NSMutableArray alloc] init];
		yammerGroupsActivityGroupCountsList = [jsonFinal valueForKey:@"value"];
		MSGraphYammerGroupsActivityGroupCounts *yammerGroupsActivityGroupCounts = [[MSGraphYammerGroupsActivityGroupCounts alloc] initWithDictionary:[yammerGroupsActivityGroupCountsList objectAtIndex: 0] error:&nserror];

}];

[meDataTask execute];

```