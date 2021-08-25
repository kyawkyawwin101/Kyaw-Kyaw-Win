- 👋 Hi, I’m @kyawkyawwin101
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
kyawkyawwin101/kyawkyawwin101 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
makeCacheMatrix<-function(x=matrix())
	{
		inv<-NULL
		set<-function(y)
		{
			x<<-y
			inv<<-NULL
		}
		get<-function() { x }
		setinv<-function(inverse) inv<<-inverse
		getinv<-function()
			{
			inv
			}
		list(set=set, get=get, setinv=setinv,getinv=getinv)
}
cacheSolve<-function(x,...)
		{
			inv<-x$getinv()
			if(!is.null(inv))
			{
				message("Getting cached Data")
				return(inv)
			}
			data<-x$get()
			inv<-solve(data,...)
			x$setinv(inv)
			inv
		}
		
