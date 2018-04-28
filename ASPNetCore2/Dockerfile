FROM microsoft/aspnetcore-build:2.0 AS build
WORKDIR /code
COPY . .
RUN dotnet restore
RUN dotnet publish -c Release -o /output

FROM microsoft/aspnetcore:2.0
COPY --from=build /output /app
WORKDIR /app
ENTRYPOINT ["dotnet","ASPNetCore2.dll"]

