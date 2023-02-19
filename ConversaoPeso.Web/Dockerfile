FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build-env
WORKDIR /App
EXPOSE 80

COPY . ./
RUN dotnet restore
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /App
COPY --from=build-env /App/out .
ENTRYPOINT ["dotnet", "ConversaoPeso.Web.dll"]