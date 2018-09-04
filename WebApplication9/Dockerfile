FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app/WebApplication9
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build 
WORKDIR /src/WebApplication9 
COPY . .
RUN dotnet publish WebApplication9.sln -c Release -o /app/WebApplication9

FROM base AS final
WORKDIR /app/WebApplication9
COPY --from=build /app/WebApplication9 .
ENTRYPOINT ["dotnet", "WebApplication9.dll"]