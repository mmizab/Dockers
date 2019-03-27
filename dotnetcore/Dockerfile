FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build
WORKDIR /src
COPY . .
RUN dotnet restore
# change webapi folder for the apropiate one
WORKDIR /src/WebApi
RUN dotnet build WebApi.csproj -c Release -o /app

FROM build AS publish
# also here
RUN dotnet publish WebApi.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
# and here
ENTRYPOINT ["dotnet", "WebApi.dll"]
