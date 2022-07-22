# Build Stage
FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build-env

WORKDIR /app

COPY . .

RUN dotnet restore
RUN dotnet publish -c release -o /app Worker.csproj

# Serve Stage
FROM mcr.microsoft.com/dotnet/aspnet:5.0

WORKDIR /app

COPY --from=build-env /app/ .

ENTRYPOINT ["dotnet", "Worker.dll"]