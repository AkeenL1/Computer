* The things a data intensive application does (processing, storage, analysis, etc.) are generally though of as being different tools, however many new tools are optimized for a variety and combination of different use cases
* Many applications have demanding & wide-ranging data requirements that cannot be met by only a single tool. Selecting, maintaining and combining these tools together with modifications to data for the tool is usually necessary
* Combining and hiding the implementation of these tools effectively creates a special purpose data system
* There are many factors  that dictate the design of this data system but there are 3 general concerns most important to consider
	* [[Reliability]] - the system working correctly in the face of adversity
	* [[Scalability]] - the system should handle growth as it grows
	* [[Maintainability]] - People working on the system should be able to maintain the systems current behavior and adapt the system to new uses *productively*
